# Macro Analysis for Portfolio Management

I created the following two indicators to make a better investment decision.
- Real investment cycle indicators for U.S, Europe and Japan
- Hard data index and Soft data index for U.S

Statistical techniques applied are:
- Hodrick-Prescott (HP) Filter
- Dickey-Fuller unit root test
- Cointegration test
- Granger Causality test
- VAR Analysis
- PCA Analysis

I used [EViews](https://www.eviews.com/home.html), a well-known statistical package for econometrics, for these analyses.

**Relevant working experience:** March 2013 to July 2018 as a portfolio manager at Korea Investment Management (Seoul, KR)

## I. Real Investment Cycle Indicators
I collected investment data in real terms from the national accounts of each country/region, U.S., Europe and Japan. I excluded investments in construction because I believed it's more relevant to my analysis.

![real_investment_cycle_indicators](real_investment_cycle_indicators.jpg)


I followed a textbook, classical way of time-series analysis. My assumptions are:
- Y = T + S + C + I,
  - where T: Trend, S: Seasonal, C: Cyclical, I: Irregular
 
 With this assumption, I remove seasonality (by gatering Seasonally Adjusted raw data) and random variations (by 3-month moving average) of my data. Then, I further remove *trend*. EViews helped very much here.


![hp_filter](hp_filter.jpg)
This chart above is not really the final indicator, but this gets you a good sense of how to decompose trend and cycle from the raw data.

Now I tranform it into natural log space. That is, I take *log*(cyclical component). In fact, I apply the HP filter to this transformed-data. I substract this trend component from the time-series data with seasonality and random variations removed. Finally, I take an exponential and then multiply it by 100 to get the final indicator going around 100.



## II. Hard data vs Soft data
### Hard data index, Soft data index and US Real GDP YoY
![hard_data_index_plot](hard_data_index_plot.jpg)

### Statistical techniques applied
Again, EViews is used.

#### Unit root test
![hard_data_index_dickey_fuller_unit_root_test](hard_data_index_dickey_fuller_unit_root_test.jpg)


#### Cointegration test
![hard_data_index_vs_us_real_gdp_cointegration_test](hard_data_index_vs_us_real_gdp_cointegration_test.jpg)


#### Granger Causality test
![hard_data_index_causes_us_real_gdp_granger_test](hard_data_index_causes_us_real_gdp_granger_test.jpg)


### An application in Asset Allocation
![asset_allocation_indicators](asset_allocation_indicators.jpg)


