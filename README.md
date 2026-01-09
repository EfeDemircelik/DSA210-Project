# Analysis of the Relationship Between BIST100 and CSI300 Stock Markets
## Project Overview
This project aims to conduct a data driven analysis of the relationship between Turkish stock market (BIST100) and Chinese stock market (CSI300) using historical daily price data. 

## Motivation
In financial analysis, the relationships between BIST100 and western markets like S&P500, or BIST100's connection with local indicators like USD/TRY exchange rate, are well known and documented. However, global economy is dynamic. This project seeks to unravel the connection between two dynamic and significant markets, Turkey and China, and answer the question: Is there a meaningful, quantifiable relationship between the Turkish and Chinese stock markets?

## Objectives
1. Examine the historical relationship between BIST100 and CSI300
   * Analyze the daily price movements of the BIST100 and CSI300 indices to identify potential long-term trends and connections.
2. Global Benchmark Comparison
   * Use MSCI World Index to compare the risk and performance of both indices against the global market.
3. Quantify the Correlation Between Market Returns
   * Analyze whether Turkish and Chinese stock market move together or independently.
4. Causality & Prediction
   * Use machine learning and time-series tests (Random Forest and Granger Causality) to determine if one market predicts the other.
------------
## Data Sources
This project will use publicly available data.
1. Borsa Istanbul 100 Index (BIST100) from investing.com
   * Daily historical data (Date, price, open, high, low, volume, daily return) for the last 10 years (2015-2025)
2. China A50 Index (CSI300) from investing.com
   * Daily historical data (Date, price, open, high, low, volume, daily return) for the last 10 years (2015-2025)
Price and daily return data will be used for visualization and hypothesis testing. Volatility of daily returns will be calculated and visualized.
3. MSCI World Index from investing.com
   * Daily historical data as a global benchmark for risk analyis.
-----------
## Data Analysis
### 1. Data Collection and Cleaning
  * Historical stock price data for BIST100 (XU100.IS) and CSI300 (000300.SS) indices will be retrieved from investing.com.
  * Due to different public holidays, there will be days when one market is open while the other is closed. These non-matching dates will be handled.
### 2. Exploratory Data Analysis (EDA)
  * Key statistics like mean, median, standart deviation will be calculated for daily returns for each index. 
  * Data visualization: 
      - Time series plots: Historical prices of both indices will be ploted on the same graph to visually identify major trends.
      - Histograms: The distribution of daily returns of both BIST100 and CSI300 will be ploted to show their spread.
      - Scatter plot: A scatter plot will be created to show the indices' relationship.
### 3. Correlation Analysis 
  * The statistical relationship between BIST100 and CSI300 will be quantified by calculating the Pearson's correlation coefficient and Spearman rank correlation coefficient.
-----------
## Hypothesis 
* Null Hypothesis (H₀): There is no significant correlation between daily returns of BIST100 and CSI300 Index.
* Alternative Hypothesis (H₁): There is a statistically significant correlation between the daily returns of BIST100 and CSI300 Index.

### Sub-Period Analysis 
* Null Hypothesis (H₀): The correlation between BIST100 and CSI300 remains constant across Pre-Covid (2017-2019), Covid (2020-2021), Post-Covid (2022,2024) periods.
* Alternative Hypothesis (H₁): The correlation structure differs significantly between the pandemic and non-pandemic periods.

### Global Risk Comparison (MSCI Benchmark)
* Null Hypothesis (H₀): BIST100 and CSI300 exhibit the same risk (Beta) relative to MSCI World Index.
* Alternative Hypothesis (H₁): BIST100 and CSI300 have significantly different risk profiles relative to the global market.
-----------
## Machine Learning and Causality Analysis
* Stationarity Testing: Used the Augmented Dickey-Fuller (ADF) test to ensure time series data was stationary (p < 0.05)before modeling.
* Predictive Modeling:
    1. Baseline: Linear and Logistic Regression.
    2. Advanced: Random Forest Classifier with balanced class weights to handle the "Always Up" inflationary bias in the Turkish market.
* Causality Testing: Performed the Granger Causality Test (lags 1-3) to check if CSI300 returns statistically "cause" or lead BIST100 returns.
* Market Regimes: Applied K-Means Clustering to identify "hidden" market states based on volatility and returns.
-----------
## Findings and Results
1. Correlation vs Causality:
   * While we found a statistically significant correlation between the markets, the Granger Causality Test yielded p-values > 0.05, proving there is no directional causal relationship. China does not "lead" Turkey; rather, they likely react to shared global factors.
2. The Inflationary Bias:
   * The BIST100 exhibits a strong drift due to domestic inflation. Standard models failed. Using a Balanced Random Forest, we improved the detection of market drops, identifying that Volatility is a stronger predictor than price changes.
3. Market Regimes:
   * Regime 0: High BIST returns, low volatility.
   * Regime 1: Turkey drops independently of China.
   * Regime 2: High volatility in both markets (e.g., Covid-19) where correlation is strongest.
