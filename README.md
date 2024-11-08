# Portfolio-Metrics-and-Factor-Exposure-Analysis

## Overview
This project draws from the Research paper ‘Fundamental Indexation’ by Robert D. Arnott, Jason Hsu, and Philip Moore and applies quantitative investment analysis techniques to construct, rank, and evaluate portfolios based on fundamental metrics, using data from CRSP, Compustat, and Fama-French factor datasets. The objective is to analyze the performance and factor exposures of various portfolios constructed from top-ranking stocks by metrics such as Book Value, Income, Dividends, Sales, and Market Cap, aiming to measure returns, volatility, and risk-adjusted performance across different market conditions.

## Data Sources
- CRSP Monthly Data: Provides monthly stock return, volume, and price data.
- Compustat Annual Data: Contains fundamental variables (Book Value, Earnings, Dividends, and Sales).
- Fama-French Monthly Data: Includes factors like Market Risk Premium, SMB (Size), HML (Value), and the Risk-Free Rate.

## Key Steps

### Data Preparation:

- CRSP Data: Adjusted to monthly values, transformed closing prices to absolute values, calculated market capitalization.
- Compustat Data: Processed to create metrics available with a 6-month lag to avoid look-ahead bias.
- Data Merging: CRSP and Compustat data merged on a monthly basis, with forward-filled metrics.

### Portfolio Construction:

- Ranked stocks by various fundamental metrics (Book Value, Earnings, Dividends, Sales, Market Cap) and selected the top 1000 stocks monthly.
- Calculated weight for each selected stock based on metric ranking and lagged weights to avoid look-ahead bias.
- Portfolio returns calculated using weighted returns of top stocks.

### Performance Evaluation:

#### Metrics calculated over two periods (1962-2004 and 2005-2023):
- Annualized Return & Volatility: Standard risk-return measures.
- Sharpe Ratio: Measures risk-adjusted returns.
- Excess Return vs. Reference: Compares each portfolio's return to the Market Cap-weighted portfolio.
- CAPM and FF3 Analysis: Assessed factor exposure and alpha relative to the market and SMB/HML factors, with statistical significance (t-stats).

## Results and Findings

### 1962-2004 Period:

- Performance: The Sales (SALE) and Dividends (DVT) portfolios outperformed with annualized returns of approximately 13.7% and 12.7%, respectively, versus the Market Cap-weighted portfolio’s 12.1%.
- Sharpe Ratios: The DVT portfolio displayed the highest risk-adjusted return (Sharpe Ratio of 0.51), followed by SALE (0.50), indicating strong returns relative to volatility.
- Excess Returns: SALE and IB portfolios achieved excess returns of 1.6% and 0.9% over the Market Cap portfolio, suggesting value in fundamental indexing during this period.
- CAPM and FF3 Analysis: Both SALE and DVT portfolios displayed positive, statistically significant alphas (CAPM Alpha ~2%), signaling potential for returns beyond market exposure alone.

### 2005-2023 Period:

- Performance: Annualized returns for most factor-based portfolios were lower than the reference Market Cap portfolio (11.5%). SEQ, IB, and DVT showed reduced returns, around 10-10.3%.
- Sharpe Ratios: Reference portfolio maintained a Sharpe Ratio of 0.67, while factor-based portfolios like SEQ and IB exhibited lower risk-adjusted performance.
- Excess Returns: All factor portfolios underperformed relative to the Market Cap portfolio, with negative excess returns and weaker risk-adjusted performance.
- CAPM and FF3 Analysis: The Reference portfolio achieved the only statistically significant alpha (1.2%), while other portfolios displayed negligible or negative alphas, highlighting market efficiency challenges in recent years.

## Insights and Best Practices
- Avoid Look-Ahead Bias: Lag fundamental data by six months.
- Forward-Fill Missing Values: Ensures consistent metric availability in merged datasets.
- Portfolio Weighting: Adjust weights monthly based on fundamental rankings.
- Factor Exposure Analysis: Use CAPM and Fama-French 3-Factor models to understand the impact of market, size, and value factors.

## Files Included
- FamaFrenchMonthly.csv: Fama-French factor data.
- Compustat_Annual.feather and CRSP_Monthly.feather: Compustat and CRSP datasets for portfolio construction and analysis.

## Future Improvements
- Explore alternative metrics or factor models (e.g., momentum, profitability) for additional insights.
- Apply other risk-adjusted measures (e.g., Sortino Ratio) for deeper portfolio evaluation.
- Extend analysis to newer factor models, such as the Carhart 4-factor model.

This project provides a comprehensive framework for constructing and evaluating portfolios based on fundamental indexing and quantitative factor exposure, yielding valuable insights into the role of various financial metrics in risk-adjusted performance across market cycles
