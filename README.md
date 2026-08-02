# SpaceY vs SpaceX: Predicting Falcon 9 First Stage Landing Success 🚀

Predicting whether the first stage of a SpaceX Falcon 9 rocket will land successfully, using historical launch data, exploratory analysis, and machine learning classification.

## 📌 Problem Statement

SpaceX advertises Falcon 9 rocket launches at a fraction of the cost of competitors ($62M vs $165M+), largely because SpaceX **reuses the first stage** of the rocket instead of discarding it. If the first stage lands successfully, it can be refurbished and flown again.

If we can predict whether a landing will succeed *before* a launch, a competing company (referred to here as "SpaceY") could estimate SpaceX's launch cost and bid more competitively for contracts. This project builds that prediction pipeline end-to-end — from raw data collection to a trained classification model and an interactive dashboard.

## 🔍 Project Workflow

This project follows a full data science pipeline, broken into stages (each as a separate notebook):

| Stage | Notebook | What it does |
|---|---|---|
| 1️⃣ Data Collection (API) | `jupyter-labs-spacex-data-collection-api (1).ipynb` | Pulls historical launch data from the SpaceX REST API |
| 2️⃣ Data Collection (Web Scraping) | `jupyter-labs-webscraping (2).ipynb` | Scrapes additional Falcon 9 launch records from Wikipedia |
| 3️⃣ Data Wrangling | `labs-jupyter-spacex-Data wrangling (1).ipynb` | Cleans data and engineers the target label (`class`: landing success/failure) |
| 4️⃣ EDA with SQL | `jupyter-labs-eda-sql-coursera_sqllite (2).ipynb` | Explores the dataset using SQL queries (SQLite) |
| 5️⃣ EDA with Visualization | `DV0101EN-Assignment-Exploring-and-Preparing-Data.ipynb` | Visual analysis of trends — payload, launch site, orbit type, and success rate |
| 6️⃣ Launch Site Analysis | `lab_jupyter_launch_site_location (1).ipynb` | Geographic analysis of launch sites using Folium maps |
| 7️⃣ Machine Learning Prediction | `SpaceX_Machine Learning Prediction_Part_5.ipynb` | Builds and evaluates classification models to predict landing success |
| 8️⃣ Interactive Dashboard | `spacex-dash-app.py` | A Plotly Dash web app for exploring launch outcomes interactively |

## 📊 Dataset

- Historical Falcon 9 launch records collected via the **SpaceX REST API** and **Wikipedia web scraping**
- Key features: launch site, payload mass, orbit type, booster version, flight number, and landing outcome
- Target variable: `class` — whether the first stage landing was successful (1) or not (0)

## 🛠️ Tech Stack

- **Python** — Pandas, NumPy
- **Data Collection** — Requests (API), BeautifulSoup (web scraping)
- **Database** — SQLite (SQL-based EDA)
- **Visualization** — Matplotlib, Seaborn, Folium (maps), Plotly
- **Machine Learning** — Scikit-learn (classification models)
- **Dashboard** — Dash / Plotly Dash

## 📈 Dashboard Features

The `spacex-dash-app.py` file launches an interactive web dashboard that lets users:
- Select a launch site from a dropdown (or view all sites)
- View a pie chart of successful launches by site
- Filter launches by payload mass range using a slider
- View a scatter plot showing the relationship between payload mass and landing success, colored by booster version

## 🚀 How to Run

**Notebooks:**
1. Clone this repository
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn folium plotly requests beautifulsoup4 jupyter
   ```
3. Run the notebooks in order (1 → 7) in Jupyter Notebook or Google Colab

**Dashboard:**
```bash
pip install dash pandas plotly
python spacex-dash-app.py
```
Then open the local URL shown in the terminal (usually `http://127.0.0.1:8050`) in your browser.

## 💡 Key Insights

- Landing success rate improves significantly with more recent flights, reflecting SpaceX's learning curve
- Certain launch sites and orbit types show higher success rates than others
- Payload mass and booster version are strong predictors of landing outcome

## 📁 Files

- `jupyter-labs-spacex-data-collection-api (1).ipynb` — Data collection via SpaceX API
- `jupyter-labs-webscraping (2).ipynb` — Data collection via web scraping
- `labs-jupyter-spacex-Data wrangling (1).ipynb` — Data cleaning and preprocessing
- `jupyter-labs-eda-sql-coursera_sqllite (2).ipynb` — SQL-based exploratory analysis
- `DV0101EN-Assignment-Exploring-and-Preparing-Data.ipynb` — Visualization-based EDA
- `lab_jupyter_launch_site_location (1).ipynb` — Launch site geographic analysis
- `SpaceX_Machine Learning Prediction_Part_5.ipynb` — Model building and evaluation
- `spacex-dash-app.py` — Interactive Dash dashboard

## 🔮 Future Improvements

- Add model comparison table (Logistic Regression, Decision Tree, SVM, KNN) with accuracy metrics
- Hyperparameter tuning with GridSearchCV
- Deploy the Dash app on a cloud platform (Render, Heroku) for public access
- Add a `requirements.txt` file for easier setup

---

**Author:** Prince
