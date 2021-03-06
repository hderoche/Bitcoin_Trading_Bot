# Bitcoin_Trading_Bot
### Disclaimer: This is a trading bot to demonstrate the power of combining TAlib with jupyter notebook to come up with trading automation strategies. It's not intended as investment advice. I have not included the order thresholds. (FYI 21/12/20 to 03/01/21 this bot was indeed profitable but use it as your own risk) 

Bitcoin trading bot built for binance exchange. The bot aims to trade between BTC(bitcoin) and a stable coin (USDT). The goal would be to sell BTC when its price is predicted to go down, and buy when BTC price is expected to go up. 
Using the trading indicators RSI and EMA5/13 average. The RSI thresholds are traditionally 70/30 for overbought and oversold. Instead of setting thresholds this project aims to use Jupyter notebooks to estimate the thresholds and provide a supplement for the candlestick patterns.

Requirements:
1. Install Talib, Pandas and binance client
2. Signup for an account in binance and get the API, secret keys
3. Jupyter notebook either Anaconda or simply fire up on a browser

Procedure:
--> Query via klines the 1minute BTC USDT data from binance   
--> Wait till the candle is closed before starting the RSI calculation  
--> Use TAlib to estimate EMA 13 and 5 period  
--> Get 4/8 hour chunks of data and pass them onto Jupyter notebook (stored in data folder)  
--> Formulate the thresholds by looking at the chart (code not included)  
--> Rerun the bot with the thresholds  

Integration:
Run the bot and collect csv file  
Edit the cell, and run the Jupyter notebook to get trading strategy  

As shown below for the 4 hour chunk between 02/01 and 03/01:
When the dots are small, and has a lighter hue: Sell at RSI < 40, 13EMA crossover
When the dots are big, and has a darker hue: Buy at RSI > 60, 13EMA crossover: the dots are big, and heavier hue

![](https://github.com/vijayengineer/Bitcoin_Trading_Bot/blob/main/assets/Screenshot%202021-01-03%20at%2015.42.01.png)
