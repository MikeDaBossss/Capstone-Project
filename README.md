# Capstone-Project
My capstone project where I try to find better returns than the S&P 500. The time period is from 2009 - 2019 and I tried 3 different methods. There are lots of ways to find better returns than the S&P 500, but I only could find data on the S&P 500 stocks so there is a lot of missed opportunity because these are the most heavily traded stocks that don't have as much of return possibility due to their size, and the market is more efficient on these stocks than other smaller stocks in the rest of the thousands of stocks. 

I used a google colaboratory notebook which is a juypter notebook inside on a web browser connected to googles computers. It uses python and I used the following libraries in my code.
1. Sklearn 
2. Graphviz
3. Requests
4. Matplotlib
5. Numpy
6. Pandas 
7. Datetime
8. Inflect
9. Json 

I followed the OSEMN process. 
1. Obtain Data
2. Scrub the data - remove unwated commas, format it the right way
3. Explore the data - look for patterns
4. Modeling the data - machine learning modeling, supervised learning
5. Interpret the results - make conclusions



The first method that I tried was using a simple moving average. When the simple moving average crosses over I would either buy or short and then wait for some movement in the price to happen. It looks like this image below.


![alt text](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTt52vhuWETR35eaabpC5_eXXGxpE-jBTRV59C0uDAFwAL-96uQaw&s)


The algorithm in english
Function # 1 Moving Average
1. Given a day and stock closing price data find that day in the data
2. Go back from that day until reaching the moving average number ( 10 ) 
3. Calculate the average of the closing price range

Function # 2 Finding Buys and Shorts
1. Given stock data, 2 moving averages, stop loss, and a profit target find all the buys or shorts
2. Loop through all the days
3. Find where the moving average had been below the other moving average 2 days ago but now has moved above
4. Save these in a list these are the buys
5. If the moving average 2 days ago was above the other moving average but now has moved below
6. Save these as the shorts

Function # 3 When to sell the shorts and buys
1. Look if current day is a day to sell off because of max_wait time being too long ( the holding period was too big )
2. Look if the current day is a sell day on a buy or short trade because of the price 
3. If there are price targets being met or the max wait time is too big then sell, remove the order from the order list, add the money back into the money counter, and record the profit
4. If there are any buys that day make the purchase and record the money spent


Method # 2 
Function # 1 Momentum Rotate
1. Given stock data, a holding period, and a list of stocks find the highest momentum stocks and buy them continually finding the newest highest momentum and selling off lower momentum stocks. 
2. Each 1.5 month time period I would implement that strategy, recording the money, accounting for commissions, and buying an equally balanced amount of the top 5 highest momentum stocks for the last 6 months. 

Method # 3 
Function # 1 Nearest Financial
1. Given a stock ticker and a day I find the nearest previous financial statement
2. Loop through all the days of possible financial statement days for that ticker
3. Make a list of all the difference in days between the statements and the certain day.
4. Sort the list by smallest difference
5. return the day of the financial statement with the smallest difference

Function # 2 Indexing the certain stock column
1. In the finances dataframe find the columns of the certain ticker that has the date and ticker name.

Function # 3 Index nearest financial
1. Given a day and a ticker find the index value of the nearest financial
2. Loops through and finds the value of that index 

I did the same functions for the financial ratios also. 

Function # 4 Return percent
1. Given a sell day, ticker, and amount of days to calculate the return for find the return percent.
2. Look for the nearest day that has the lowest absolute difference to the amount of days from the sell date 
3. Then calculate the return percent

Function # 5 get finance and ratio
1. Combines all the previous functions together
2. Creates a financials for all the stocks and financial ratios dataframe
3. Combines these together and adds the column names

Function # 6 Y returns
1. Find the returns for all the stocks and see if they exceed the minimum return

Function # 7 Percent returns
1. Find the returns for all the stocks

Function #8 results
1. Given a random forest prediction and the real returns and a percent goal find the return given the prediction being a buy.



My resuts were bad but I did not have enough computing resources to test out enough stocks, price actions, and moving averages. 


![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/SMA.png)

The second method that you will find in my code is a momentum strategy. It is based on the idea that stocks that have been winning in the past will be winning in the future. That is momentum and that is the strategy that I used. I buy the top 5 highest returning stocks in the last 6 months and I recalculate every month. This method worked very well and I almost tripled the market returns with this method. 


![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/Momentum3Mo.png)



![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/Momentum6Mo.png)

The third method that you will see is a random forest method that involves a lot of the lines of code as it is the most complex to do. It uses a random forest decision tree to find what financial characteristics winning stocks had previously and then uses that to calculate which stocks will win in the future given a certain financial profile of a company. I came up with this methodology myself and I had mixed results since I could not compute the calculations enough I'm not sure that it is a winning strategy, but I was able to get a market return of 11%. With some more tuning of the random forest, more feature engineering such as more financial momentum features, and price features I think that it would be winning more than the market.

This is a picture of the S&P 500 price over the same time period.
![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/SP500.png)
