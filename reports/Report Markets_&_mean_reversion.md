# Markets & Mean Reversion

In [Price vs Earnings](https://github.com/TheProfitPilgrim/mf_research_reports/blob/main/reports/Report%20Indices_Price_vs_Earnings.md), I tried to make an [direction predictor](https://mfproject.streamlit.app/index_ptr) using Mean reversion idea. Here I look at this idea in detail

Tldr 🥱😴 :

[Data](https://github.com/TheProfitPilgrim/mf_research_reports/tree/main/reports/report_src/mf_index_analysis/Data/india_data) : Daily Price, PE, Earnings of Nifty 50 for past 26 years

## Experiment 1

1. Start recording the PE of Nifty 50 daily from Jan 1. 
2. Continue to record the daily PE on one track and on the first day of 2005, calculate the mean, median PE using ALL the data collected until that point.
3. Now apart from recording the daily PE, also compute the mean, median PE daily using all the previous PE data.

Now in 2025 plot all the mean, median PE values of Nifty 50 from 2005 : 

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture59.png) 

There is clearly an increasing trend for the cumulative mean, median PE. Maybe black swans like covid and fin crisis are distorting? Remove years 2008,9 and 2020,21

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture60.png) 

The upward trend still persists. 

Lets check the same graph for S&P 500 (From 1943 - 2024))

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture64.png) 

We can see that in the past 25 yrs, there is a clear upward drift in the median PE across both S&P 500 and the Nifty 50. Why is this? Is this expected to continue? 

I was expecting the curves to be a lot flatter. 

## Experiment 2 : 

1. Start with all the historical (99-25) PE values.
2. Calculate the 80th and 20th percentile of PE.
3. Go through each day from start of data and if that day's PE is : 
    1. Lesser than 20th percentile : Calculate the number of days it takes from that day to get *above* 20th percentile and store it in undervalued category
    2. Higher than 80th percentile : Calculate the number of days it takes from that day to get *below* 80th percentile and store it in overvalued category 
    3. B/w the two : Ignore and continue

The above has a flaw : Data look ahead bias (since future data is being used to calculate the 80th and 20th percentiles). But its main purpose is comparison b/w overval and underval cases. 

### 80-20 case :

Now the average of the overvalued category is ~338 days whereas the average of the undervalued category is ~156 days.

Distribution of overval & underval days : 

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture61.png) 

How does this change if we look at over percentile combos : 90/10 (extremes), 70/30 (moderate)? 

### 90-10 case :

Overvalued : ~108 days, Undervalued : ~61 days
It makes perfect sense - since its more extremeity, both movements are happening faster but the relation b/w them still holds good

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture62.png) 

### 70-30 case :

Overvalued : ~311 days, Undervalued : ~182 days
Again perfectly inline with expectation

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture63.png) 

* Thus markets stay "overvalued" for almost twice as long as being "undervalued" on average 

## Checking for mean reversion in PE values

For the following statistical tests, the book Algorithmic Trading : Winning Strategies and their Rationale by Ernst P Chan has been used as reference. 

> The mathematical description of a mean-reverting price series is that the change of the price series in the next period is proportional to the difference between the mean price and the current price. 

### ADF + P-values

Mean reverting series of values are stationary - constant mean, variance over time. Lets first check for stationarity. 

ADF test + P values : with ADF test, if we reject null hypothesis it indicates that the data is stationary. 

ADF = -3.43 ; P-value = 0.0099

The negative ADF value of -3.43 and  P value < 0.01 (==>99% confidence level) indicate that the null hypothesis is very strongly being rejected, i.e, that ***the PE data is stationary***

### Half-life of mean reversion

Half life = ~273 days. This means that mean reversion for the market's PE from deviation doesn't happen in the short-term (like in a couple of months or qtrs) 

### Hurst Exponent 

Another check for mean reversion is Hurst Exponent. > 0.5 means trending, <0.5 means mean-reverting and 0.5 means random walk

The Hurst exponent values is ~0.47 which shows that its weakly mean reverting
