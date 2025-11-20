# Stock Volatility Prediction Using Machine Learning and News Sentiment

## Overview
This group project investigates predicting next-day stock volatility by combining traditional financial data (from Yahoo Finance) with alternative data sources, including Reddit and HackerNews sentiment. Multiple models were implemented and evaluated:

- **Baseline:** GARCH(3,3)  
- **Machine Learning Models:** XGBoost (regression), Logistic Regression (classification), Random Forest (classification)
- **Deep Learning:** LSTM (RNN)

The goal was to determine if sentiment data could improve volatility predictions beyond historical price-based patterns.

---

## My Contributions
I specifically contributed to:  

- **Data Cleaning & Preprocessing:** Financial and sentiment data were cleaned, merged, and aligned with trading days.  
- **Feature Engineering:** Lagged features, realized volatility, and sentiment indicators were created, carefully avoiding data leakage.  
- **GARCH Implementation:** Created baseline volatility forecasts using the `arch` package.  
- **Logistic Regression Model:** Implemented a classification baseline; performance was poor compared to other models and omitted from the final analysis.  
- **XGBoost:** Implemented per-ticker regression model for next-day volatility prediction.
- **Mathematical Support:** Assisted with interpreting evaluation metrics and providing theoretical guidance for the Random Forest and LSTM models implemented by teammates.
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
  - **`Random_Forest.ipynb`** - Python Random Forest classification model
  - **`LSTM_RNN.ipynb`** - Python Long Short-Term Memory network

- **Final Paper** - Comprehensive project report written collaboratively by the team (PDF)
---

## Running the Code
- All `.ipynb` scripts can be run in Google Colab.  
