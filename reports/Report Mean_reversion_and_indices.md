# Markets & Mean Reversion

In [Price vs Earnings](https://github.com/TheProfitPilgrim/mf_research_reports/blob/main/reports/Report%20Indices_Price_vs_Earnings.md), I tried to make an [direction predictor](https://mfproject.streamlit.app/index_ptr) using Mean reversion idea. Here I look at this idea in detail

Tldr 🥱😴 :

[Data](https://github.com/TheProfitPilgrim/mf_research_reports/tree/main/reports/report_src/mf_index_analysis/Data/india_data) : Daily Price, PE, Earnings of Nifty 50 for past 26 years

## Experiment 1

1. Start recording the PE of Nifty 50 daily from Jan 1. 
2. Continue to record the daily PE on one track and on the first day of 2005, calculate the mean, median PE using ALL the data collected until that point.
3. Now apart from recording the daily PE, also compute the mean, median PE daily using all the previous (including yesterday's) PE data.

Now in 2025 plot all the mean, median PE values of Nifty 50 from 2005 : 

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture59.png) 

There is clearly an increasing trend for the cumulative mean, median PE. Maybe black swans like covid and fin crisis are distorting? Remove years 2008,9 and 2020,21

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture60.png) 

The upward trend still persists. 

Why is this? Is the Indian stock market getting more and more overvalued in general? Is it due to the changing dominant sector of companies (say like IT vs Bank) and thus people are willing to pay a higher multiple? Is this expected to continue? 

I was expecting the curve to be a lot flatter

## Experiment 2 : 

1. Start with all the historical (99-25) PE values.
2. Calculate the 80th and 20th percentile of PE.
3. Go through each day from start of data and if that day's PE is : 
    1. Lesser than 20th percentile : Calculate the number of days it takes from that day to get *above* 20th percentile and store it in undervalued category
    2. Higher than 80th percentile : Calculate the number of days it takes from that day to get *below* 80th percentile and store it in overvalued category 
    3. B/w the two : Ignore and continue

### 80-20 case :

Now the average of the overvalued category is ~338 days whereas the average of the undervalued category is ~156 days.

* Thus markets stay overvalued for almost twice as long as being undervalued on average 

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


