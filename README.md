# Stock Volatility Prediction Using Machine Learning and News Sentiment

## Overview
This group project investigates predicting next-day stock volatility by combining traditional financial data (from Yahoo Finance) with alternative data sources, including Reddit and HackerNews sentiment. Multiple models were implemented and evaluated:

- **Baseline:** GARCH(3,3)  
- **Machine Learning Models:** XGBoost (regression), Linear Regression (regression)    

The goal was to determine if sentiment data could improve volatility predictions beyond historical price-based patterns.

---

## My Contributions
I specifically contributed to:  

- **Data Cleaning & Preprocessing:** Financial and sentiment data were cleaned, merged, and aligned with trading days.  
- **Feature Engineering:** Lagged features, realized volatility, and sentiment indicators were created, carefully avoiding data leakage.  
- **GARCH Implementation:** Created baseline volatility forecasts using the `arch` package.  
- **Linear Regression Model:** Implemented a regression baseline; performance was poor compared to other models and omitted from the final analysis.  
- **XGBoost:** Implemented per-ticker regression model for next-day volatility prediction.  

---

## Models

### Baseline: GARCH
- GARCH(3,3) fitted per ticker using past price returns.  
- Forecasts next-day volatility independently for each stock.  
- Average RMSE: 0.0115  

### Linear Regression
- Implemented as a simple regression baseline.  
- Used lagged volatility, sentiment, and volume features.  
- Poor performance relative to other models; omitted from final comparisons.    

### XGBoost (Regression)
- Per-ticker regression model for next-day volatility.  
- Average RMSE: 0.0069  
- Sentiment features improved accuracy modestly.    

---

## Folders
- **`1 Year Data`** — Preprocessing, feature engineering, and merging sentiment and financial data
  - **`FINAL_1YEAR_DATA.csv`** - Final combined Yahoo, Reddit, and HackerNews data  
  - **`News1year.csv`** - One year of HackerNews data  
  - **`yahooredditcombined.csv`** - Final combined Yahoo and Reddit data  
  - **`combineall.ipynb`** - Python script for combining all data  
  - **`yahooreddit.ipynb`** - Python script for combining Yahoo and Reddit data  

- **`3 Year Data`** — Preprocessing, feature engineering, and merging sentiment and financial data
  - **`3year_finance_data.csv`** - 3 years of Yahoo finance data  
  - **`Combined_3year_data.csv`** - 3 years of combined Yahoo, Reddit, and HackerNews data  
  - **`year3news.csv`** - 3 years of HackerNews data  
  - **`combining_3yr_data.ipynb`** - Python script combining 3 years of Yahoo, Reddit, and HackerNews data  

- **`Webscrape`** — Pulling Reddit, Yahoo Finance, and HackerNews data
  - **`4240commentscrape.ipynb`** - Python script to scrape Reddit comments  
  - **`4240webscrape.ipynb`** - Python script to scrape Yahoo Finance data and run GARCH model  
  - **`BigQueryScript.ipynb`** - SQL script to query HackerNews data in Google BigQuery. Must be run in BigQuery  
  - **`bqData.ipynb`** - Python script pulling and cleaning HackerNews data  

- **`MODELS`** — Forecasting models run and tested
  - **`garch_volatility_predictions.csv`** - GARCH results  
  - **`Logistic_Regression.ipynb`** - Python Logistic Regression model; omitted from analysis  
  - **`XGBoostModel.ipynb`** - Python XGBoost model  

---

## Running the Code
- All `.ipynb` scripts can be run in Google Colab.  
- Make sure to mount Google Drive and update file paths as needed:  
```python
from google.colab import drive
drive.mount('/content/drive')
