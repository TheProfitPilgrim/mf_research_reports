# Markets & Mean Reversion

In [Price vs Earnings](https://github.com/TheProfitPilgrim/mf_research_reports/blob/main/reports/Report%20Indices_Price_vs_Earnings.md), I tried to make an [direction predictor](https://mfproject.streamlit.app/index_ptr) using Mean reversion idea. Here I look at this idea in detail

Tldr 🥱😴 :

[Data](https://github.com/TheProfitPilgrim/mf_research_reports/tree/main/reports/report_src/mf_index_analysis/Data/india_data) : Daily Price, PE, Earnings of Nifty 50 for past 26 years

Imagine a little experiment : 

1. Year is 1999 and one starts recording the PE of Nifty 50 daily from Jan 1. 
2. They continue to record the daily PE on one track and on the first day of 2005, a new calculation of the mean, median PE using ALL the data collected until that point begins.
3. Now apart from recording the daily PE, they also compute the mean, median PE daily using all the previous (including yesterday's) PE data.

Now in 2025 they plot all the mean, median PE values of Nifty 50 from 2005 : 

There is clearly an increasing trend for the cumulative mean, median PE. I thought black swans like covid and fin crisis were distorting so I removed those years but the upward trend still persists. 
image.png
Why is this? Is the Indian stock market getting more and more overvalued in general? Is it due to the changing dominant sector of companies (say like IT vs Bank) and thus people are willing to pay a higher multiple? Is this expected to continue? 

I was looking from a reversion to mean/median PE angle and wanted to see if the median itself was moving. I was expecting a more flat curve across time but I'm surprised by the upward trend.

## Experiment 1 : 

1. Collect all the historical PE values.
2. If one 

