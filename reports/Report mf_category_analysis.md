# MF Category Analysis

[The active SEBI circular regarding this](https://www.sebi.gov.in/legal/circulars/oct-2017/categorization-and-rationalization-of-mutual-fund-schemes_36199.html) : 6th Oct 2017

[Addition of flexicap funds](https://www.sebi.gov.in/legal/circulars/nov-2020/circular-on-introduction-of-flexi-cap-fund-as-a-new-category-under-equity-schemes_48108.html) : 6th Nov 2020

[AMFI](https://www.amfiindia.com/investor-corner/knowledge-center/SEBI-categorization-of-mutual-fund-schemes.html)  

SEBI classifies MFs into 5 categories : Equity, Debt, Hybrid, Solution Oriented and Other Schemes

Data : ['consolidated-sheet'](https://docs.google.com/spreadsheets/d/1Wt2c9Jm5qCvfWe2BfyWQ23WQ7o5U3l_OvS1q4byt9S4/edit?gid=987646402#gid=987646402) (Has 1391 total funds)

Then used [List of benchmark index for each category](https://www.amfiindia.com/research-information/other-data/listofbenchmarkindices) to get the benchmark for each fund

##  Funds with Nifty 500 as benchmark

Lets filter the funds which have Nifty 500 as benchmark

 The dataset is static and it was created on Nov 10, 2024 so that will be used as the latest date for return calculations.

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
2. Suppose top 20 funds are picked based on best 3 month recent return and 3 of the funds have existed for only 5 months, then for the mean calculation of 6 month and higher periods, these will be excluded. A minimum of 75% of the funds must have a particular data point to calculate average. 

### Picking the top N 3-month toppers from this list

|Portfolio size (funds) | 3m absolute | 6m absolute | 1y absolute | 3y cagr   | 5y cagr   | 10y cagr     |
|------------------|-------------|-------------|-------------|-----------|-----------|--------------|
| 5                | 8.09        | 20.66       | 52.01       | 19.68     | 17.62     | Only 2/5     |
| 10               | 7.08        | 19.62       | 47.24       | Only 7/10 | Only 6/10 | Only 3/10    |
| 25               | 5.45        | 16.79       | 42.59       | Only 17/25| Only 14/25| Only 10/25   |
| 50               | 4.36        | 14.82       | 37.66       | 13.60     | Only 30/50| Only 20/50  |

Same as above table but with excess returns over Nifty 500 : 

| N in Top N funds | 3m absolute | 6m absolute | 1y absolute | 3y cagr | 5y cagr | 10y cagr |
|------------------|-------------|-------------|-------------|---------|---------|----------|
| 5                | 9.30        | 10.03       | 20.78       | 6.26    | -0.90   | -        |
| 10               | 8.29        | 8.99        | 16.01       | -       | -       | -        |
| 25               | 6.66        | 6.15        | 11.36       | -       | -       | -        |
| 50               | 5.57        | 4.19        | 6.43        | 0.18    | -       | -        |







