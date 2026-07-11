# 📈 Indian Market Volatility Forecasting System 

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![Machine Learning](https://img.shields.io/badge/ML-Random%20Forest-orange.svg)](https://scikit-learn.org/)
[![Market Data](https://img.shields.io/badge/Data-NSE%20%7C%20BSE-green.svg)](https://yahoo-finance.md)

An end-to-end predictive analytics system designed to forecast the volatility of the Indian stock market (specifically the Nifty 50 index) using historical official data. By leveraging quantitative finance methodologies and machine learning, this system engineers key statistical features to predict next-day market risk.

---

## 🛠️ Tech Stack & Keywords
* **Core Analytics:** Python, Pandas, NumPy
* **Machine Learning:** Scikit-Learn (Random Forest Regressor)
* **Data Sourcing:** Yahoo Finance API (`yfinance`)
* **Visualization:** Matplotlib
* **Domain Focus:** Volatility Forecasting, Risk Modeling, Financial Time-Series Analysis
  
---

## 🚀 Features
- **Automated Data Pipeline:** Fetches historical and live-updated NSE/BSE market data dynamically.
- **Quantitative Feature Engineering:** - Computes log returns for statistical consistency.
  - Generates annualized 21-day rolling realized volatility targets.
  - Crafts auto-regressive features using past volatility lags ($t-1$, $t-2$, $t-5$).
- **Lookahead Bias Prevention:** Implements chronological time-series splitting (80% Train / 20% Test) instead of randomized shuffling to ensure robust, real-world backtesting.
- **Automated Visualization Export:** Generates performance comparison charts and safely saves them into an isolated `images/` directory.

---

## 📂 Project Structure

```text
├── notebook.ipynb                      # Interactive Jupyter Notebook pipeline
├── NCMPCS abstract.pdf                 # Reseacrh Abstract
├── NCMPCS research documentation.pdf   # Research documentation
└── README.md
```
---

## 📊 Model Performance & Insights
The system was evaluated against the out-of-sample testing set, achieving highly precise metrics capturing market regime shifts:

* Root Mean Squared Error (RMSE): 0.0157R-squared
* ($R^2$) Score: 0.9051

---
## 📊 Graph

<img width="616" height="330" alt="Screenshot 2026-07-12 013323" src="https://github.com/user-attachments/assets/e1188955-4a7d-433f-9c99-b55dd063e3e8" />
<img width="617" height="326" alt="Screenshot 2026-07-12 013333" src="https://github.com/user-attachments/assets/5981133b-4376-43bf-9083-2427eccd03bc" />


## Summary
The $R^2$ score of ~90.5% demonstrates that the Random Forest model, combined with auto-regressive volatility lag features, successfully learns the non-linear properties of volatility clustering (the financial phenomenon where high-volatility periods follow high-volatility periods, and vice versa) without needing strict parametric assumptions like classical GARCH frameworks.

---
