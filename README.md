# Capstone-Project
My capstone project where I try to find better returns than the S&P 500. The time period is from 2009 - 2019 and I tried 3 different methods. There are lots of ways to find better returns than the S&P 500, but I only could find data on the S&P 500 stocks so there is a lot of missed opportunity because these are the most heavily traded stocks that don't have as much of return possibility due to their size, and the market is more efficient on these stocks than other smaller stocks in the rest of the thousands of stocks. 



The first method that I tried was using a simple moving average. When the simple moving average crosses over I would either buy or short and then wait for some movement in the price to happen. It looks like this image below.


![alt text](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTt52vhuWETR35eaabpC5_eXXGxpE-jBTRV59C0uDAFwAL-96uQaw&s)

My resuts were bad but I did not have enough computing resources to test out enough stocks, price actions, and moving averages. 


![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/SMA.png)

The second method that you will find in my code is a momentum strategy. It is based on the idea that stocks that have been winning in the past will be winning in the future. That is momentum and that is the strategy that I used. I buy the top 5 highest returning stocks in the last 6 months and I recalculate every month. This method worked very well and I almost tripled the market returns with this method. 


![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/Momentum3Mo.png)



![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/Momentum6Mo.png)

The third method that you will see is a random forest method that involves a lot of the lines of code as it is the most complex to do. It uses a random forest decision tree to find what financial characteristics winning stocks had previously and then uses that to calculate which stocks will win in the future given a certain financial profile of a company. I came up with this methodology myself and I had mixed results since I could not compute the calculations enough I'm not sure that it is a winning strategy, but I was able to get a market return of 11%. With some more tuning of the random forest, more feature engineering such as more financial momentum features, and price features I think that it would be winning more than the market.

This is a picture of the S&P 500 price over the same time period.
![alt text](https://github.com/MikeDaBossss/Capstone-Project/blob/master/SP500.png)
