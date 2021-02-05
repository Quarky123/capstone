- Identifies which of the three proposals you outlined in your lightning talk you have chosen
- Articulates the main goal of your project (your problem statement)
- Outlines your proposed methods and models
- Defines the risks & assumptions of your data 
- Revises initial goals & success criteria, as needed
- Documents your data source
- Performs & summarizes preliminary EDA of your data

Data source: Quandl

## Problem Statement
### Context / Motivation
PEAD stands for post earnings announcement drift and simply put, is the tendency for a stock’s cumulative abnormal returns to drift in the direction of an earnings surprise for several weeks (even several months) following an earnings announcement. It is a well documented phenomenon in the finance industry, is one of major earnings anomalies, which supports the counterargument against market efficiency theory (Ball & Brown, 1968). However, PEAD’s effects on certain baskets of stocks are not entirely known, particularly, those stocks that tend to be more illiquid due to their relatively smaller size in terms of market capitalisation, volume traded per day and available float. Some studies have been done on the PEAD associated with small cap stocks, which is defined as companies with market capitalisation of between 300 million USD to 2 billion USD and it is found that the PEAD for small cap stocks is almost always larger than the PEAD associated with large cap stocks (Bird, Choi & Yeung , 2011). However, there has been little research done on microcap stocks, which are defined as stocks with a market capitalisation of less than 300 million USD and given that they are even more illiquid than small cap stocks, it is expected that the PEAD effect would be even larger.


https://www.jstor.org/stable/2490232?seq=1
https://www.uts.edu.au/sites/default/files/wp15.pdf


### Primary & secondary audience
The primary audience would be portfolio manager of the quantitative team as he needs to understand if the results are significant enough to be incorporate as a strategy.

The secondary audience would be both the potential and existing investors in the fund that seek to understand or predict how this would impact the overall fund performance and risk profile.

### Business problem statement
As part of an attempt to understand if a strategy based around PEAD and other variants of the same concept would create performance alpha in the microcap world, the quantitative team of a multi-strategy investment fund was put in charge of backtesting how a portfolio worth $ 1 million would had perform between  2015-01-02 and 2020-12-18, which is a timeline of roughly 5 years. The fund utilises a core satellite portfolio management strategy, thus if successful, this strategy will be incorporate into the main fund under the satellite portfolio as an attempt to generate alpha.


### Data Science problem statement
The team is tasked to find the optimal overall portfolio performance using different variations of PEAD which takes into account different factors such as earnings, corporate releases and other news. The optimal portfolio will be the portfolio with the best portfolio metrics which includes the likes of a high sharpe ratio, and low maximum drawdown. The problem can be tackled with time series analysis which includes methods such as…

The portfolio allocation will be done in a binary manner, where a certain percentage of the fund’s NAV will be allocated based if a stock meets the criteria, and the position will then be unwind later based on the criteria set.


Risks & Assumptions
-	No transaction cost
-	No market impact
-	No inflation

Risks
-	Might not be able to handle all these data sets
