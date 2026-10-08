# Stock returns before and after COVID-19

In this project I looked at how Apple, Tesla and Amazon stocks behaved before and after COVID-19 (split at 11 March 2020, when the WHO declared the pandemic).

I made this project for my Foundation Year at the University of Siena and got 28/30 for it. Later I came back to it, fixed some mistakes and extended the analysis.

## Files
- `stock_returns_covid.ipynb` - the original version I submitted
- `stock-returns-covid-fixedversion.ipynb` - the fixed and extended version
- `data/prices.csv` - saved prices, so the results don't change if Yahoo updates its data
- `requirements.txt` - library versions

## What I did
- downloaded daily prices from 2016 to 2025 using yfinance
- calculated daily log returns
- calculated yearly return, volatility, skewness and kurtosis for each period
- made charts of prices and histograms of returns

## What I fixed later
- in the histograms I multiplied daily returns by 252 by mistake, now they show daily returns in %
- the stocks are now matched by date, not by row number
- 11 March 2020 was missing from the data, now it is included in "Before COVID"
- simplified the log return calculation using pandas

## What I added later
- SPY (S&P 500) as a benchmark, to see which changes were market-wide and which were specific to the stocks
- the years after COVID are split in two: the COVID shock (2020-2021) and after COVID (2022-2025), to see if the effect faded
- Sharpe ratio using the T-bill rate as the risk-free rate, beta to the market and max drawdown
- rolling volatility, rolling correlation with the market and drawdown charts
- tests to check if the changes are statistically significant (Levene, Welch t-test, Mann-Whitney)
- written explanations and conclusions inside the notebook

## Results
- all three stocks became more volatile after COVID, and the volatility did not go back to the old level
- 2020-2021 had very high returns (Tesla 117% a year, Apple 53%), but in 2022-2025 all three earned less than before COVID
- the change in average return is not statistically significant, only the change in volatility is
- the stocks started to follow the market more closely, for example Tesla's beta went from 1.34 to 2.03
- the biggest drawdowns were in the 2022 bear market (Tesla -73%, Amazon -52%), not in the 2020 crash
- kurtosis was between 5 and 19, much higher than 3 (normal distribution), so big jumps in price happen more often than a normal distribution would predict

## How to run
```
pip install -r requirements.txt jupyter
jupyter notebook stock-returns-covid-fixedversion.ipynb
```

## Tools
Python, NumPy, pandas, SciPy, Matplotlib, yfinance
