## Project and Author info
Project: Ames Housing Prices <br />
Author: Dennis Chan Zhen Ye


## Contents 
- [01_data_cleaning](code/01_data_cleaning.ipynb)
- [02_eda](code/02_eda.ipynb)
- [03_Conclusion](code/03_Conclusion.ipynb)
- [Datasets](datasets)
- [Presentation](presentation/DSI%20-%20project%202.pdf)

## Data Dictionary 


## Problem Statement
**Context / Motivation** <br />

might have to change this if i can't pull of PEAD

PEAD stands for post earnings announcement drift and simply put, is the tendency for a stock’s cumulative abnormal returns to drift in the direction of an earnings surprise for several weeks (even several months) following an earnings announcement. It is a well documented phenomenon in the finance industry, is one of major earnings anomalies, which supports the counterargument against market efficiency theory (Ball & Brown, 1968). However, PEAD’s effects on certain baskets of stocks are not entirely known, particularly, those stocks that tend to be more illiquid due to their relatively smaller size in terms of market capitalisation, volume traded per day and available float. Some studies have been done on the PEAD associated with small cap stocks, which is defined as companies with market capitalisation of between 300 million USD to 2 billion USD and it is found that the PEAD for small cap stocks is almost always larger than the PEAD associated with large cap stocks (Bird, Choi & Yeung , 2011). However, there has been little research done on microcap stocks, which are defined as stocks with a market capitalisation of less than 300 million USD and given that they are even more illiquid than small cap stocks, it is expected that the PEAD effect would be even larger.

https://www.jstor.org/stable/2490232?seq=1
https://www.uts.edu.au/sites/default/files/wp15.pdf




**Primary & secondary audience** <br />
The primary audience would be portfolio manager of the quantitative team as he needs to understand if the results are significant enough to be incorporate as a strategy.

The secondary audience would be both the potential and existing investors in the fund that seek to understand or predict how this would impact the overall fund performance and risk profile.


**Business problem statement** <br />
As part of an attempt to understand if a strategy based around PEAD and other variants of the same concept would create performance alpha in the microcap world, the quantitative team of a multi-strategy investment fund was put in charge of backtesting how a portfolio worth $ 1 million would had perform between  2015-01-02 and 2020-12-18, which is a timeline of roughly 5 years. The fund utilises a core satellite portfolio management strategy, thus if successful, this strategy will be incorporate into the main fund under the satellite portfolio as an attempt to generate alpha.

**Data Science problem statement** <br />
The team is tasked to find the optimal overall portfolio performance using different variations of PEAD which takes into account different factors such as earnings, corporate releases and other news. The optimal portfolio will be the portfolio with the best portfolio metrics which includes the likes of a high sharpe ratio, and low maximum drawdown. The problem can be tackled with time series analysis which includes methods such as…

The portfolio allocation will be done in a binary manner, where a certain percentage of the fund’s NAV will be allocated based if a stock meets the criteria, and the position will then be unwind later based on the criteria set.





## Executive Summary
**Intention** <br />
<!-- This report provides a predictive analysis of the housing sale prices surrounding Ames, a city in Iowa. Methods of analysis used in this report include the use of trend analysis, clasifications based on statistics such as mean median mode, encoding of data, as well as the use of regression analysis tools such as lasso, ridge, and elastic net. The data are also fitted into the regression analysis tool with the highest mean cross-validation score. In this case it happens to be the lasso model. -->

**Process** <br />
<!-- Given that the target (Sale Price) is a continuous varaible, linear regression models will be used. The process flow is as follows. -->

1. [Data Cleaning](code/01_data_cleaning.ipynb)
 - Data validation
 - Replacement/Imputation of null values with median and 'Unknown'
 - Removal of Outliers

2. [Exploratory Data Analysis (EDA)](code/02_eda.ipynb)
 - Histogram and Distribution Analysis
 - Scatterplot Analysis
 - Box Plot Analysis
 
3. [Model Prep and Feature Engineering](code/02_eda.ipynb)
 - Feature engineering using get_dummies

3. [Business Insights](code/02_eda.ipynb)
 - Comments on correlation and adding value to the house


4. [Model Selection and Evaluation](code/03_Conclusion.ipynb)
 - Creating features and target vector
 - Instantiating Linear Regression Models (`Standard Linear`, `Lasso`, `Ridge`, and `ElasticNet`)
 - Model Selection based on Cross Validation Score
 - Model Fitting and Evaluation
 - Predicting the actual test
 - Kaggle Score


**Key Findings** <br />
Results of the data analysed show that certain neighborhoods command higher mean and median sale prices with StoneBr having the highest median price and MeadowV with the lowest. The report also finds the use of predictive analysis on sale prices of homes in the Aimes region based on the variables provided by the dataset is successful in predicting the sale prices of other (unknown) house prices in the same region as seen from the low kaggle score of 27355.18333. 




## Recommendations and Conclusion
<!-- As stated above, the model is useful for predicting house prices in the region and the predictions generated by this model could be used as input for the prediction of mortgage default risk. However, a major area of weakness is that it only provides a snapshot of what house prices between the 2006 to 2010 period, which coincidentally spans across the '08 financial crisis which was in large part due to RMBS products, specifically due to subprime mortgages who are then put into the RMBS. Thus, this may not be the price of houses in this area during normal market conditions. As such, the predictions generated by this model is likely only within the stated period. If the user hopes to generate house prices in the year 2030, it is likely to be inaccurate due to factors such as inflation which affects house prices. <br />

Besides the usefulness of the model as an input for credit default risk, other business applications could also be derived from the results. Overall Quad appears to add the most value to a home as it has a coeff of 0.803, which means that the dependent variable (Overall Quad) is expected to increase when that independent variable (SalePrice increases by one). The Id hurts the value of a home the most, perhaps there is some hidden meaning behind the Id where certain Id (for example smaller numbers) are given to more expensive areas and vice versa. However, it would be hard to speculate. Enclosed Porch with a corr of -0.135713 is the next most negatively correlated with SalePrice. Homeowners could improve could revamp the overall material and finish of the house to increase the value of the house. An investment in houses located in StoneBr is most likely to be a good investment because it has the largest interquartile range which could mean that by revamping the purchased house, the investor could command a good return on their investment. However, the results of the data might not translate well into other areas. It will likely generalise other cities with similar geography as Aimes, but it would not work for cities such as New York where spaces are scarce and land is expensive. 
 -->

## Citation
