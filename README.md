# Stock returns before and after COVID-19

In this project I looked at how Apple, Tesla and Amazon stocks behaved before and after COVID-19 (split at 11 March 2020, when the WHO declared the pandemic).

I made this project for my Foundation Year at the University of Siena and got 28/30 for it. Later I came back to it and fixed some mistakes.

## Files
- `stock_returns_covid.ipynb` - the original version I submitted
- `stock-returns-covid-fixedversion.ipynb` - the fixed version

## What I did
- downloaded daily prices from 2016 to 2025 using yfinance
- calculated daily log returns
- calculated yearly return, volatility, skewness and kurtosis for each period
- made charts of prices and histograms of returns

## Results
- after COVID all three stocks became more volatile
- Tesla had the biggest change: yearly return went from about 25% to 43%, but risk also went up a lot
- Amazon's return went down (about 25% to 17%) while its risk went up
- kurtosis was between 6 and 10, much higher than 3 (normal distribution), so big jumps in price happen more often than a normal distribution would predict

## What I fixed later
- in the histograms I multiplied daily returns by 252 by mistake, now they show daily returns in %
- the stocks are now matched by date, not by row number
- 11 March 2020 was missing from the data, now it is included in "Before COVID"
- simplified the log return calculation using pandas

## Tools
Python, NumPy, pandas, SciPy, Matplotlib, yfinance
