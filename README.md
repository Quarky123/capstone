## Project and Author info
Project:
Author: Dennis Chan Zhen Ye


## Contents
- [Data Cleaning](code/01_data_cleaning.ipynb)
- [Exploratory Data Analysis (EDA)](code/02_eda.ipynb)
- [Model Prep and Predictions](code/03_data_cleaning_for_PEAD_and_EPS_STD_Predictions.ipynb)
- [Portfolio Allocation using PEAD](code/04_PEAD.ipynb)
- [Returns Calculation](code/05_returns_calculation.ipynb)
- [Evaluation and Conclusion](code/06_Evaluation_and_Conclusion.ipynb)
- [Datasets](datasets)
- [Presentation](presentation/Presentation.pdf)

## Data Dictionary
- a full list of the data dictionary can be found on [Quandl](https://www.quandl.com/databases/SF1/data) 

## Problem Statement
**Context / Motivation** <br />
PEAD stands for post earnings announcement drift and simply put, is the tendency for a stock’s cumulative abnormal returns to drift in the direction of an earnings surprise for several weeks (even several months) following an earnings announcement. It is a well documented phenomenon in the finance industry, is one of major earnings anomalies, which supports the counterargument against market efficiency theory (Ball & Brown, 1968). However, PEAD’s effects on certain baskets of stocks are not entirely known, particularly, those stocks that tend to be more illiquid due to their relatively smaller size in terms of market capitalisation, volume traded per day and available float. Some studies have been done on the PEAD associated with microcap stocks, which is defined as companies with market capitalisation of between 300 million USD and it is found that the PEAD for small cap stocks is almost always larger than the PEAD associated with large cap stocks (Bird, Choi & Yeung , 2011). However, there has been little research done on microcap stocks, which are defined as stocks with a market capitalisation of less than 300 million USD and given that they are even more illiquid than small cap stocks, it is expected that the PEAD effect would be even larger.

The PEAD effect is measured using the SUE model. SUE stands for standardised unexpected earnings model and the (SUE) model the model also pointed out that the drifting magnitude is more obvious in small-cap firms than the large one. This report constructs SUE model with quarterly report data of the microcap market.


SUE = (EPS(Q1) - fEPS(Q1))/SD(Q1)

Where:

EPS(Q1) – the earnings per share reported for a given quarter
fEPS(Q1) – the forecasted or anticipated earnings per share for a company during the same quarter
SD(Q1) – the standard deviation of estimated earnings for the specified quarter


https://www.jstor.org/stable/2490232?seq=1
https://www.uts.edu.au/sites/default/files/wp15.pdf




**Primary & secondary audience** <br />
The primary audience would be portfolio manager of the quantitative team as he needs to understand if the results are significant enough to be incorporate as a strategy.

The secondary audience would be both the potential and existing investors in the fund that seek to understand or predict how this would impact the overall fund performance and risk profile.


**Business problem statement** <br />
As part of an attempt to understand if a strategy based around PEAD and other variants of the same concept would create performance alpha in the microcap world, the quantitative team of a multi-strategy investment fund was put in charge of backtesting how a portfolio worth $ 1 million would had perform between  2015-01-02 and 2020-12-18, which is a timeline of roughly 5 years. The fund utilises a core satellite portfolio management strategy, thus if successful, this strategy will be incorporate into the main fund under the satellite portfolio as an attempt to generate alpha.

**Data Science problem statement** <br />
The team is tasked to compare the overall portfolio performance using a PEAD strategy vs a simple buy and hold strategy of the S&P500 index. The problem can be tackled with time series analysis which includes methods such as ARIMA. The use of the SUE formula is also needed in deriving which stock positions to take.

Success of the project will be evaluated on two fronts:
First, based on how close the forecasted EPS are to the actual EPS. This can be done using the SMAPE loss function.
Second, determining if the strategy is able to surpass the benchmarket portfolio (S&P500) by comparing them using traditional portfolio metrics which includes the likes of sharpe ratio and cumulative returns. The portfolio with a higer sharpe ratio higher cumulative returns would be the winner in that regard.




## Executive Summary
**Intention** <br />
This report provides a predictive analysis of the earnings per share of the next few quarters for each of the stock listed in the basket of stocks selected as well as an evaluation of whether the PEAD strategy outperforms the S&P500 index. Methods of analysis used in this report include the use of trend analysis, clasifications based on statistics such as mean median mode, encoding of data and the use of time series analysis and ARIMA analysis as well as the SMAPE loss function.


**Process** <br />
Given that the target (EPS) is a time series, ARIMA models will be used. The process flow is as follows.

1. [Data Cleaning](code/01_data_cleaning.ipynb)
 - Filter by market cap
 - Obtain daily stock price and volume data
 - Daily Metrics of Filtered Tickers
 - Feature Engineering
 - Final Export 

2. [Exploratory Data Analysis (EDA)](code/02_eda.ipynb)
 - Basic EDA and Feature Engineering
 - Time Series Analysis
 - Correlation Analysis
 - Analysis of Fundamentals
 
3. [Model Prep and Predictions](code/03_data_cleaning_for_PEAD_and_EPS_STD_Predictions.ipynb)
 - Data Preprocessing
 - ARIMA and Naive Models
 - Forecasting EPS and STD

4. [Portfolio Allocation using PEAD](code/04_PEAD.ipynb)
 - SUE Calculations
 - Portfolio Backtesting
 - Final NAV

5. [Returns Calculation](code/05_returns_calculation.ipynb)
 - Preprocessing for backtesting
 - Portfolio backtesting
 - Calculating final NAV
 
6. [Evaluation and Conclusion](code/06_Evaluation_and_Conclusion.ipynb)
 - Cumulative Returns
 - Rolling Sharpe Ratio
 - Drawdown



**Key Findings** <br />
- The report finds that use of ARIMA to predict the subsequent EPS is rather successful as seen from the low SMAPE score as compared to a naive prediction. 
- The report also concludes that a portfolio strategy using PEAD to allocate capital is unable to outperform that of the S&P index on both metrics such as cumulative returns and rolling sharpe ratio.


## Recommendations and Conclusion
As stated above, the model is useful for predicting EPS of the subsequent quarter of each stock and the predictions generated by this model could be used as input for the SUE and subsequently used to backtest a trading strategy.

However, the model is also unlikely to outperform the S&P500 index as mentioned above. Thus, it is not recommended to include the PEAD strategy as a means of incorporating alpha into the core satellite portfokio

A major area of weakness of predicting the EPS is that it is essentially a backward looking model. Such that, the long term forecast eventually goes to be straight line and poor at predicting series with turning points. Thus, the model would had failed given the onset of the coronavirus pandemic which caused the markets to tumble as a whole with little or no regards to the EPS.

Also, the liquidity of various microcap stocks may be limited due to the low float and daily traded volume for many of the stocks stated above. Thus, making this strategy infeasible for larger funds even if the strategy managed to create alpha.

## Citation
Ball, R., &amp; Brown, P. (1968). An empirical evaluation of accounting income numbers. Journal of Accounting Research, 6(2), 159. doi:10.2307/2490232
Bird, R. G., Choi, D. F., &amp; Yeung, D. (2011). Market uncertainty and sentiment, and the post-earnings announcement drift. SSRN Electronic Journal. doi:10.2139/ssrn.1912195
