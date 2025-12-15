# Avatar: Fire and Ash - Box Office Prediction Project

## Project Overview
This project is an end-to-end machine learning pipeline designed to predict the global box office revenue of the upcoming movie **"Avatar: Fire and Ash"** (Release Date: Dec 19, 2025).

The project involves web scraping over 3,500 movies, engineering features related to "hype" (YouTube trailer views), and training time-series aware regression models to forecast the financial success of the film.

## Objective
- **Data Collection:** Scrape metadata (budget, runtime, genres) from **TMDB** and digital footprint data (trailer views) from **YouTube**.
- **Modeling:** Train and tune a **Gradient Boosting Regressor** to predict revenue.
- **Inference:** Estimate the global box office for *Avatar: Fire and Ash*.

## Tech Stack
- **Language:** Python 3.x
- **Libraries:** Pandas, NumPy, Scikit-Learn, Matplotlib, Seaborn, SHAP
- **Scrapers:** `tmdbv3api` (The Movie Database), `yt-dlp` (YouTube)
- **Environment:** Google Colab / Jupyter Notebook

## Repository Structure
```
Avatar-Fire-and-Ash-Box-Office-Prediction/
├── Box\_Office\_Prediction.ipynb   \# Main Colab notebook with all code
├── data/
│   ├── raw\_movie\_data.csv            \# Raw scraped data from TMDB/YouTube
│   └── final\_movie\_data.csv          \# Cleaned and processed data used for training
├── models/
│   └── box\_office\_model.pkl          \# Serialized final model (Joblib)
├── README.md                         \# Project documentation
└── requirements.txt                  \# List of dependencies

````

## How to Run
1. **Clone the Repository**
   ```bash
   git clone [https://github.com/mashroorhssn/Avatar-Fire-and-Ash-Box-Office-Prediction.git](https://github.com/mashroorhssn/Avatar-Fire-and-Ash-Box-Office-Prediction.git)
    ````

2.  **Install Dependencies**
    ```bash
    pip install tmdbv3api yt-dlp pandas numpy scikit-learn matplotlib seaborn shap joblib
    ```
3.  **API Configuration**
      - You need a valid **TMDB API Key**.
      - Open the notebook and replace `'YOUR_API_KEY_HERE'` with your key in the "Configuration" step.
4.  **Run the Notebook**
      - Execute the cells in order. The scraping step (Step 2) may take 1-2 hours to fetch all 5,000 movies.

## Methodology

1.  **Scraping:** Automated script fetches high-revenue movies across Sci-Fi, Action, and Adventure genres.
2.  **Feature Engineering:**
      - `is_sequel`: Heuristic to detect franchise films.
      - `trailer_views`: Proxy for audience anticipation/hype.
      - `budget`: The strongest predictor of revenue.
3.  **Validation:** Used **Time-Series Split** (Train on pre-2023, Test on 2023-2025) to prevent data leakage.
4.  **Model Selection:** Compared Linear Regression, Random Forest, and Gradient Boosting.
5.  **Explainability:** Used **SHAP values** to interpret feature importance.

## Results

  - **Best Model:** Gradient Boosting Regressor (Tuned)
  - **Performance (on unseen future data):** R² Score \~0.40
  - **Key Insight:** `Budget` and `Trailer Views` were the top two drivers of revenue.

### Final Prediction for *Avatar: Fire and Ash*

Based on estimated inputs (Budget: $400M, Trailer Views: \~30M+), the model predicts:

> **Predicted Global Box Office:** \~$1,039,533,540.60

## 📜 Credits

  - **Author:** K. M. Mashroor Hossain
  - **Course:** Applied Machine Learning
  - **Data Sources:** [TMDB](https://www.themoviedb.org/), YouTube

<!-- end list -->

```
```
