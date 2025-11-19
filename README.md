# Stock Volatility Prediction Using Machine Learning and News Sentiment

## Overview
This project investigates predicting next-day stock volatility by combining traditional financial data (from Yahoo Finance) with alternative data sources, including Reddit and HackerNews sentiment. Multiple models were implemented and evaluated:

- **Baseline:** GARCH(3,3)  
- **Machine Learning Models:** Random Forest (classification), XGBoost (regression), Linear Regression (regression)  
- **Deep Learning:** LSTM (RNN)  

The goal was to determine if sentiment data could improve volatility predictions beyond historical price-based patterns.

---

## My Contributions
I specifically contributed to:  

- **Data Cleaning & Preprocessing:** Financial and sentiment data were cleaned, merged, and aligned with trading days.  
- **Feature Engineering:** Lagged features, realized volatility, and sentiment indicators were created, carefully avoiding data leakage.  
- **GARCH Implementation:** Created baseline volatility forecasts using the `arch` package.  
- **Linear Regression Model:** Implemented a regression baseline; performance was poor compared to other models and omitted from the final analysis.  

---

## Data
The repository includes:  

- `combined_df.csv` — Cleaned stock price data  
- `HackerNews.csv` & `Reddit.csv` — Raw sentiment/comment data  
- `year3news.csv` & `News1year.csv` — Processed sentiment features per day per ticker  
- `yfinance_final.csv` — Stock price data for modeling  

> All datasets are provided for reproducibility and transparency.

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

### Random Forest (Classifier) - Not included in this repository
- Predicts top 30% high-volatility days using lagged volatility and sentiment features.  
- F1 (positive class): 0.75  
- Feature importance shows realized volatility dominated; sentiment provided incremental improvement.  

### XGBoost (Regression) - Not included in this repository
- Per-ticker regression model for next-day volatility.  
- Average RMSE: 0.0069  
- Sentiment features improved accuracy modestly.  

### LSTM (RNN) - Not included in this repository
- Time-aware model using sequential lagged volatility, sentiment, and volume features.  
- Average RMSE: 0.0070  
- Captures temporal dependencies and trends more effectively than baseline or ML models.  

---

## Files
- `data_cleaning.py` — Preprocessing, feature engineering, and merging sentiment and financial data  
- `garch_model.py` — GARCH(3,3) baseline implementation  
- `ml_models.py` — Random Forest, XGBoost, LSTM, and Linear Regression model implementations  
- `final_paper.pdf` — Detailed report of methodology, results, and analysis  
- `data/` — Raw and processed datasets  

---

This README documents only my own contributions and the final project scope and analysis.

