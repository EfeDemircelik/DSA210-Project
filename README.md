# Analysis of the Relationship Between BIST100 and CSI300 Stock Markets
## Project Overview
This project aims to conduct a data driven analysis of the relationship between Turkish stock market (BIST100) and Chinese stock market (CSI300) using historical daily price data. 
-------------
## Motivation
In financial analysis, the relationships between BIST100 and western markets like S&P500, or BIST100's connection with local indicators like USD/TRY exchange rate, are well known and documented. However, global economy is dynamic. This project seeks to unravel the connection between two dynamic and significant markets, Turkey and China, and answer the question: Is there a meaningful, quantifiable relationship between the Turkish and Chinese stock markets?
-----------
## Objectives
1. Examine the historical relationship between BIST100 and CSI300
   * Analyze the daily price movements of the BIST100 and CSI300 indices to identify potential long-term trends and connections.
2. Quantify the Correlation Between Market Returns
   * Analyze whether Turkish and Chinese stock market move together or independently.
------------
## Data Sources
This project will use publicly available data.
1. Borsa Istanbul 100 Index (BIST100) from Yahoo Finance
   * Daily historical data (Date, open, high, low, close, adj close, volume) for the last 10 years (2015-2025)
2. China A50 Index (CSI300) from Yahoo Finance
   * Daily historical data (Date, open, high, low, close, adj close, volume) for the last 10 years (2015-2025)
-----------
## Data Analysis
### 1. Data Collection and Cleaning
  * Historical stock price data for BIST100 (XU100.IS) and CSI300 (000300.SS) indices will be retrieved from Yahoo Finance using Python's yfinance library.
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
* Alternative Hypothesis (H₁): There is a significant correlation between the daily returns of BIST100 and CSI300 Index.
