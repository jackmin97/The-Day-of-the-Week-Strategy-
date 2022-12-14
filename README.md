# The-Day-of-the-Week-Strategy-
In this notebook, we will create and backtest a strategy on the Day of the Week anomaly on Bitcoin. The strategy aims to exploit the anomaly that the returns on a particular day are significantly higher compared to the other days. 

The strategy works as follows:

### 1. Import the data
First, we will import the necessary libraries, read the BTC-USD data and plot the close price series.

### 2. Calculate the percentage change for each day.
The pct_change() computes the percentage change from the immediately previous row by default. That is the change in value in percentage terms from the previous day's close to today's close price. For example, if yesterday's close price is USD 10 and today's close price is USD 11, then the percentage change is 10%.

The day wise Sharpe ratio is computed using te groupby function, which groups the
percent change day wise, the mean (mean()) and the standard deviation(std()) of the returns.

### 3. Using the data for the last 60 days, determine the Day of the Week on which the returns or the Sharpe ratio was the highest.
The day wise Sharpe ratio is computed for the past 60 days

For the next two weeks (14 days), we buy Bitcoin on the day with the highest Sharpe ratio (buy at previous day's close price and sell at today's close price). This is indicated by storing 1 in the signal column of the dataframe df. 0 indicates that we don't have any position in the Bitcoin.

In the dataframe df, the signal column is set to 1 on Sunday 16 September 2018, indicating that we will buy the Bitcoin (BTCUSD) on the Saturday's close price and sell the BTCUSD on Sunday's close price.

### 4. For the next two weeks, buy the bitcoin on that day (buy at the previous day's close and sell at the close of that day).

### 5. Repeat the step 3 and 4, for the entire backtesting period.

The strategy returns are generated by multiplying the signal with the daily percent change and stored in the strategy_returns.
