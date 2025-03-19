# MF Category Analysis

[The active SEBI circular regarding this](https://www.sebi.gov.in/legal/circulars/oct-2017/categorization-and-rationalization-of-mutual-fund-schemes_36199.html) : 6th Oct 2017

[Addition of flexicap funds](https://www.sebi.gov.in/legal/circulars/nov-2020/circular-on-introduction-of-flexi-cap-fund-as-a-new-category-under-equity-schemes_48108.html) : 6th Nov 2020

[AMFI](https://www.amfiindia.com/investor-corner/knowledge-center/SEBI-categorization-of-mutual-fund-schemes.html)  

SEBI classifies MFs into 5 categories : Equity, Debt, Hybrid, Solution Oriented and Other Schemes

Data : ['consolidated-sheet'](https://docs.google.com/spreadsheets/d/1Wt2c9Jm5qCvfWe2BfyWQ23WQ7o5U3l_OvS1q4byt9S4/edit?gid=987646402#gid=987646402) (Has 1391 total funds). An updated version of this with benchmarks added : ['W benchmarks']()

Then used [List of benchmark index for each category](https://www.amfiindia.com/research-information/other-data/listofbenchmarkindices) to get the benchmark for each fund

## Why this? 

* I tried forming portfolios using an arbitrary system and found it hard to evaluate the performance since each MF belongs to a category of its own with its own benchmark.
* Here I "level the playing field" (all of the funds have same benchmark) and try moving inputs around to see how the outperformance is affected 

##  Funds with Nifty 500 as benchmark

Lets filter the funds which have Nifty 500 as benchmark

 The dataset is static and it was created on Nov 10, 2024 so that will be used as the latest date for return calculations. 

 Index funds have not been considered, since they track almost except for a small tracking error.

 Nifty 500 Benchmark Performance : 

 | Time Period   | Nifty 500 Returns (%) |
|---------------|-----------------------|
| 3m absolute   | -1.21                 |
| 6m absolute   | 10.63                 |
| 1y absolute   | 31.23                 |
| 3y cagr       | 13.42                 |
| 5y cagr       | 18.52                 |
| 10y cagr      | 12.90                 |

Only the following type of funds have Nifty 500 Benchmark according to SEBI : 

 * ELSS, Flexi Cap, Dividend Yield, Value / Contra  & Focused Fund 
 * In thematic funds - Business Cycle / Special Situation, Exports, Momentum, Pioneering Innovation, Resurgent India, Sector Rotation Funds  

Notes : 
1. All the fund return table values are Arithmetic Mean of the values of individual funds in the pf with N funds (i.e, pf return if equal allocation)
2. Suppose top 20 funds are picked based on best 3 month recent return and 2/20 of the funds have existed for only 5 months, then for the mean calculation of 6 month and higher periods, these will be excluded. A minimum of 75% of the funds must have a particular data point to calculate average
3. There is no back testing or some other measure that is being done to see how effective this selection is - its just picking the **current** funds that show up and aggregating their historical performance numbers to look for something interesting.  

The following tables are concise results (standalone and comparitive) of the various formed portfolios. Though its lengthy (2 x 6 =12 tables), the data is easy to interpret and can provide insights. Only 2 parameters are being varied - one is ***selection process*** (picking the best short, mid and long term performers) and the other is ***the number of funds in the portfolio***. Skip the tables to the observations section below.   

### Picking the top 3-month toppers 

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr  | 10y cagr    |
|------------------------|-------------|-------------|-------------|-------------|---------|----------|-------------|
| 5                      | 1963.42     | 8.09        | 20.67       | 52.01       | 19.68   | 22.03    | Only 2/5    |
| 10                     | 3340.95     | 7.08        | 19.62       | 47.24       | Only 7/10 | Only 6/10 | Only 3/10   |
| 25                     | 9381.27     | 5.45        | 16.79       | 42.59       | Only 17/25 | Only 14/25 | Only 10/25 |
| 50                     | 6526.33     | 4.36        | 14.82       | 37.66       | 17.44   | Only 30/50 | Only 20/50 |

Same as above table but with excess returns over Nifty 500 : 

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 1963.42     | 9.30        | 10.04       | 20.78       | 6.26    | 3.51    | -        |
| 10.00                  | 3340.95     | 8.29        | 8.99        | 16.01       | -       | -       | -        |
| 25.00                  | 9381.27     | 6.66        | 6.16        | 11.36       | -       | -       | -        |
| 50.00                  | 6526.33     | 5.57        | 4.19        | 6.43        | 4.02    | -       | -        |

### Picking the top 6-month toppers

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 7063.04     | 6.87        | 21.47       | 50.66       | 20.15   | 22.26   | Only 3/5 |
| 10.00                  | 6039.92     | 5.51        | 20.00       | 46.04       | 18.30   | 21.64   | Only 6/10|
| 25.00                  | 4289.52     | 4.48        | 18.09       | 45.13       | 18.27   | Only 18/25 | Only 12/25 |
| 50.00                  | 5470.45     | 3.46        | 16.62       | 41.25       | 17.50   | Only 33/50 | Only 25/50 |

Excess returns over Nifty 500 : 

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 7063.04     | 8.08        | 10.84       | 19.43       | 6.73    | 3.74    | -        |
| 10.00                  | 6039.92     | 6.72        | 9.37        | 14.81       | 4.88    | 3.12    | -        |
| 25.00                  | 4289.52     | 5.69        | 7.46        | 13.90       | 4.85    | -       | -        |
| 50.00                  | 5470.45     | 4.67        | 5.99        | 10.02       | 4.08    | -       | -        |

### Picking the top 1-year toppers

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr  | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|----------|----------|
| 5.00                   | 1748.98     | 4.22        | 16.97       | 56.21       | 21.36   | Only 3/5 | Only 0/5 |
| 10.00                  | 1968.54     | 2.16        | 14.43       | 53.74       | Only 7/10 | Only 5/10 | Only 2/10 |
| 25.00                  | 4672.23     | 2.73        | 15.47       | 49.32       | 21.46   | Only 16/25 | Only 12/25 |
| 50.00                  | 6210.43     | 2.03        | 14.31       | 45.78       | 20.83   | Only 37/50 | Only 29/50 |

Excess returns over Nifty 500 : 

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 1748.98     | 5.43        | 6.34        | 24.98       | 7.94    | -       | -        |
| 10.00                  | 1968.54     | 3.37        | 3.80        | 22.51       | -       | -       | -        |
| 25.00                  | 4672.23     | 3.94        | 4.84        | 18.09       | 8.04    | -       | -        |
| 50.00                  | 6210.43     | 3.24        | 3.68        | 14.55       | 7.41    | -       | -        |

### Picking the top 3-year toppers

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 5371.57     | 1.41        | 12.75       | 46.24       | 25.03   | 25.96   | 17.35    |
| 10.00                  | 17944.60    | 2.10        | 13.64       | 45.93       | 24.31   | 26.13   | 17.14    |
| 25.00                  | 11751.49    | 1.62        | 13.23       | 43.16       | 22.84   | 25.66   | Only 15/25 |
| 50.00                  | 8088.74     | 1.55        | 13.16       | 41.21       | 21.54   | 26.07   | Only 25/50 |

Excess returns over Nifty 500 : 

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 5371.57     | 2.62        | 2.12        | 15.01       | 11.61   | 7.44    | 4.45     |
| 10.00                  | 17944.60    | 3.31        | 3.01        | 14.70       | 10.89   | 7.61    | 4.24     |
| 25.00                  | 11751.49    | 2.83        | 2.60        | 11.93       | 9.42    | 7.14    | -        |
| 50.00                  | 8088.74     | 2.76        | 2.53        | 9.98        | 8.12    | 7.55    | -        |

### Picking the top 5-year toppers

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 11810.97    | -0.90       | 8.41        | 34.01       | 20.96   | 31.73   | Only 3/5 |
| 10.00                  | 5946.85     | 0.51        | 10.15       | 30.30       | 20.47   | 30.50   | Only 3/10|
| 25.00                  | 10006.22    | 0.49        | 11.43       | 37.08       | 21.10   | 28.07   | Only 15/25 |
| 50.00                  | 9314.56     | 0.92        | 12.37       | 39.22       | 20.50   | 26.09   | Only 31/50 |

Excess returns over Nifty 500 : 

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 11810.97    | 0.31        | -2.22       | 2.78        | 7.54    | 13.21   | -        |
| 10.00                  | 5946.85     | 1.72        | -0.48       | -0.93       | 7.05    | 11.98   | -        |
| 25.00                  | 10006.22    | 1.70        | 0.80        | 5.85        | 7.68    | 9.55    | -        |
| 50.00                  | 9314.56     | 2.13        | 1.74        | 7.99        | 7.08    | 7.57    | -        |

### Picking the top 10-year toppers

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 21243.70    | -1.54       | 9.19        | 41.99       | 21.66   | 29.12   | 20.18    |
| 10.00                  | 14898.48    | -0.57       | 10.22       | 41.32       | 20.48   | 27.00   | 19.16    |
| 25.00                  | 13140.13    | 0.39        | 11.82       | 40.73       | 20.05   | 25.29   | 17.85    |
| 50.00                  | 13513.50    | 1.02        | 12.29       | 38.68       | 18.83   | 23.42   | 16.65    |

Excess returns over Nifty 500 : 

| Portfolio size (funds) | AUM average | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------------|-------------|-------------|-------------|-------------|---------|---------|----------|
| 5.00                   | 21243.70    | -0.33       | -1.44       | 10.76       | 8.24    | 10.60   | 7.28     |
| 10.00                  | 14898.48    | 0.64        | -0.41       | 10.09       | 7.06    | 8.48    | 6.26     |
| 25.00                  | 13140.13    | 1.60        | 1.19        | 9.50        | 6.63    | 6.77    | 4.95     |
| 50.00                  | 13513.50    | 2.22        | 1.66        | 7.45        | 5.41    | 4.90    | 3.75     |

## Observations

1. **Fund Size vs Performance** : *Across all the selections* (the data used for plotting is combined one with all 12) + *Across all the time periods of return like 3m, 1y* (all 6 graphs below) : There is a clear trend : 

| ![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture42.png) | ![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture43.png) |
|-----------------------|-----------------------|
| 3m | 6m |

| ![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture44.png) | ![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture45.png) |
|-----------------------|-----------------------|
| 1y | 3y |

| ![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture46.png) | ![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture47.png) |
|-----------------------|-----------------------|
| 5y | 10y |

* As number of funds in portfolio ⬇️, portfolio return ⬆️ 
* 5y returns is an exception where 25 funds perform better than 5&10
* This is not surprising, more concentrated portfolio giving better returns

2. **Fund Size vs Volatility**: Though we cannot comment on the portfolio's volatility using this data (need to consider correlation b/w funds), we can find out the average volatility of the PFs to get an idea of the volatility of the individual funds forming the PFs

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture48.png)

* This relation is not surprising. From 1, we get that concentrated portfolios perform better. The above graph shows that the funds forming these PFs are more volatile too.

3. **Fund Size vs Aum** : The average AUM increases sharply to peak at 25 funds before dropping back for the 50 funds case.

* When picking the top performing funds, the first few are generally newer funds that have shown extraordinary performance due to a time-period bias. Due to this, the average AUM is pretty low for these. 5 & 10 fall under this category

* However, I think 25 fund PFs show a balance where the funds are performing well and are big as well 

* In the 50 fund case, I think the net has become too huge and includes small funds and hence it has dropped back again. 

![Graph](https://raw.githubusercontent.com/TheProfitPilgrim/mf_research_reports/main/reports/report_media/Picture49.png)

4. **AUM vs Out Performance** : 

