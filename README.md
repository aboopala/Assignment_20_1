### Predicting Short-Term Stock Returns Using Technical Indicators

**Avanthi Boopalan**

#### Executive Summary

This project investigates whether technical price indicators can predict the direction of short-term stock returns for large-cap U.S. equities. Using historical price and volume data from Yahoo Finance, a set of technical indicators—including momentum, moving averages, volatility, and volume-based features are developed. Baseline logistic regression classifier is trained using a chronological train/ test split.

The baseline model achieved an accuracy of approximately 52% and a ROC-AUC of approximately 0.51. The model’s accuracy is comparable to a majority-class baseline, reinforcing that the model does not provide meaningful predictive improvement. These results suggest the technical indicators provide minimal predictive power for short-term stock movements in large-cap stocks.

#### Rationale

Small improvements in predicting short-term stock returns should help improve portfolio performance over time. Investors that don’t have access to data or a systematic analysis could be using intuition or be reacting to trends and the news. This project provides a data-driven framework to quantify the probability of stock returns and can help investment allocations, risk mitigation and a systematic approach to trading decisions. If we can glean actionable insights from the model, it should help improve decision-making compared to naive methods. With the influence of technology, automation and algorithmic trading in markets, applying machine learning techniques to investment analysis is more appropriate with the technological shift across industries.

#### Research Question

Can technical price indicators predict whether large-cap U.S. stocks will generate a positive return over the next five trading days?

#### Data Sources

- Yahoo Finance (via `yfinance`)
- Selected large-cap U.S. stocks:
  - AAPL, MSFT, AMZN, NVDA, META, GOOGL
- Time period:
  - January 1, 2015 – April 22, 2026

Note:
getData.ipynb contains the data acquisition workflow using yfinance. The main analysis notebook, capstone_v1.ipynb, uses the saved dataset for reproducibility. Users can rerun getData.ipynb to refresh the dataset or test alternate date ranges.

#### Methodology

1. Data acquisition using Yahoo Finance
2. Data Preparation
3. Feature engineering using technical indicators
4. Target variable creation (5-day forward return direction)
5. Exploratory Data Analysis (EDA)
6. Model training using Logistic Regression
7. Model evaluation using classification metrics and ROC-AUC
8. Interpretation of results and feature coefficients

#### Results
The logistic regression coefficients suggest the presence of weak and competing effects between momentum and mean reversion. Indicators such as the moving average ratio (MA5/MA20), price relative to the 20-day moving average, and one-day returns exhibit small positive coefficients, indicating a slight tendency toward short-term momentum.

In contrast, longer-term return measures (5-day and 10-day returns), RSI, and intraday price changes show negative coefficients, suggesting mild mean reversion effects, where recent gains may be followed by short-term pullbacks.

However, the magnitude of these coefficients is small, and the model’s overall performance (ROC-AUC ~ 0.51) indicates that these relationships are weak and do not translate into meaningful predictive power. This suggests that while certain technical patterns may exist, they are not sufficiently strong or stable to reliably predict short-term stock returns in large-cap equities.

This combination of weak momentum and mean reversion effects is consistent with the intuition that short-term stock price movements are often noisy and difficult to predict using technical indicators alone.

#### Next steps

Adding SPY market features, VIX volatility index and including industry/ sector information would help add some external aspects to only technical indicators. Also comparing with tree-based models, testing other prediction timeframes will provide more understanding and help evaluate the performance of the strategy.

#### Outline of project

- [capstone_v1.ipynb](./capstone_v1.ipynb) = main notebook
- [getData.ipynb](./getData.ipynb) = data collection
- [data/stock_data.csv](./data/stock_data.csv) = dataset

##### Contact and Further Information

Avanthi Boopalan - avanthiboopalan@gmail.com

