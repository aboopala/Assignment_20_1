## Predicting Short-Term Stock Returns Using Technical Indicators

#### Notebook Link: [Capstone Notebook](./capstone_v1.ipynb)

### Executive Summary

This project investigates whether technical price indicators can predict the direction of short-term stock returns for large-cap U.S. equities. Using historical price and volume data from Yahoo Finance, a set of technical indicators—including momentum, moving averages, volatility, and volume-based features—were engineered and used to train a logistic regression classifier.

The baseline model achieved an accuracy of approximately 52% and a ROC-AUC of approximately 0.51, indicating that it performs only marginally better than random guessing. These results suggest that technical indicators alone provide limited predictive power for short-term stock movements in large-cap equities.

---

### Problem Statement

Predicting stock price movements is a fundamental challenge in finance and machine learning. This project evaluates whether commonly used technical indicators contain enough predictive signal to determine whether a stock will generate a positive return over the next five trading days.

---

### Research Question

Can technical price indicators predict whether large-cap U.S. stocks will generate a positive return over the next five trading days?

---

### Data Sources

- Yahoo Finance (via `yfinance`)
- Selected large-cap U.S. stocks:
  - AAPL, MSFT, AMZN, NVDA, META, GOOGL
- Time period:
  - January 1, 2015 – April 22, 2026

Note:
getData.ipynb contains the data acquisition workflow using yfinance. The main analysis notebook, capstone_v1.ipynb, uses the saved dataset for reproducibility. Users can rerun getData.ipynb to refresh the dataset or test alternate date ranges.

---

### Project Workflow

1. Data acquisition using Yahoo Finance
2. Feature engineering using technical indicators
3. Target variable creation (5-day forward return direction)
4. Exploratory Data Analysis (EDA)
5. Model training using Logistic Regression
6. Model evaluation using classification metrics and ROC-AUC
7. Interpretation of results and feature coefficients

---

### Data Preparation

- Data reshaped into a stock-day level dataset
- Missing values from rolling calculations removed
- No duplicate records found
- Chronological train/test split used to avoid look-ahead bias

---

### Feature Engineering

- Momentum features (1-day, 5-day, 10-day returns)
- Trend indicators (MA ratio, price vs MA20)
- Volatility (10-day, 20-day)
- RSI (14-day)
- Volume metrics (volume change, ratio)
- Intraday features (high-low range, open-close change)

---

### Exploratory Data Analysis (EDA)

- Returns centered around zero
- Slight class imbalance (~58% positive)
- Moderate correlation between features
- Stable volume with occasional spikes

---

### Modeling Approach

- Logistic Regression baseline
- Standardization applied
- Hyperparameter tuning with time-series cross-validation
- Balanced class weights

---

### Model Evaluation

- Accuracy: ~0.52  
- Precision: ~0.56  
- Recall: ~0.54  
- F1 Score: ~0.55  
- ROC-AUC: ~0.51  

### Baselines
- Majority class accuracy: ~0.55  
- Random ROC-AUC: ~0.50  

---

### Key Findings

- ROC-AUC ≈ 0.51, indicating near-random predictive power
- Weak momentum and mean reversion signals observed
- Technical indicators alone insufficient for prediction

---

### Limitations

- Only technical indicators used
- No macro or fundamental data
- Market regime changes not modeled
- No trading cost simulation
- Possible survivorship bias

---

### Next Steps

- Add SPY/VIX features
- Try nonlinear models
- Explore longer horizons
- Simulate trading strategies

---

### Repository Structure

- capstone_v1.ipynb = main notebook
- getData.ipynb = data collection
- data/stock_data.csv = dataset

---

### Author

Avanthi Boopalan
