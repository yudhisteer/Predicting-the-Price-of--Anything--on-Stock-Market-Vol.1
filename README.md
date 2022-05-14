# Predicting the Price of "Anything" on Stock Market



## Abstract


## Research Questions

## Methods

## Plan of Action

1. Behavioral Economics: Ways people or markets misbehave

    - Efficient Market Hypothesis (EMH)
    - Random Walk Hypothesis (RWH)
    - Are markets efficient?
    - Limits to arbitrage
    - Biases and Heuristics
    - Inefficient markets
    - Irrational behavior

2. Financial Engineering: The Basics

    - Financial Data
    - Returns
    - Adjusted close, stock splits and dividends
    - Volatility Clustering


3. Understanding Time Series

    - What are time series?
    - Statistics on time series

3. Exploratory Data Analysis and Static Analysis

    - QQ Plot
    - T-distribution
    - Confidence Intervals
    - Statistical Testing
    - Covariance and Correlation
    - Alpha and Beta
    - Gaussian Mixture Model

4. Exponential Smoothing and ETS Methods

    - Simple Moving Average (SMA)
    - Exponentially Weighted Moving Average (EWMA)
    - Simple Exponential Smoothing (SES)
    - Holt's Linear Trend Model
    - Holt-Winters Model

5. ARIMA: Autoregressive Integrated Moving Average 

6. VARMA: Vector Autoregressive Moving Average

7. ANN

8. CNN

9. RNN

10. RL

-----------------

### 1. Behavioral Economics: Ways people or markets misbehave

#### 1.1 Efficient Market Hypothesis (EMH)
In order to get to know the Efficient Market Hypothesis (EMH) a bit better, we will start with a bit of history. 
#### 1.1.1 History
We will start in France in the ```1860s``` where there was a French mathematician, ```Jules Regnault```, who was one of the first authors who tried to create a ```"stock exchange science"``` based on **statistical** and **probabilistic analysis**. He was the first to suggest a modern theory of stock price changes using a ```random walk``` model.

Thirty-six years later, ```Louis Bachelier``` who also happens to be a French mathematician studied the behavior of prices in the French stock and option markets. In his seminal work, which he delivered in ```1900```, he concluded that stock price changes are ```random``` and **cannot be predicted**.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168444685-2831fe90-1515-44d9-bfc4-beddf56e0e75.png" width="800" height="290"/>
</p>

Thirty years later,  ```Alfred Cowles III``` embarked on an ambitious ```5``` year project to look for evidence that the stock market is predictable. He pours over forecasts from various sources, studies a large pool of individual stock recommendations from various financial services over the course of five years. And after all that work, he can't find any evidence that the stock market is predictable. 

In the 1950s, ```Maurice Kendall``` studied different British equity and commodity prices, and again, searches for clues and prices to predict future economic cycles.
But he only finds more evidence that prices move ```randomly```. At about the same time, stock market movements was identified as following a ```Brownian motion``` which is described as the random movement of particles in nature, as first identified by the biologist ```Robert Brown``` in the ```1800s```.

Finally, in ```1970``` the great ```Eugene Fama``` developed the **Efficient Market Hypothesis** which in simple words states that it is impossible to "beat the market" consistently.

#### 1.1.2 Defining EMH
Throughout history, we have seen a great deal of "pessimism" but let's suppose for a second we could really develop a model which could detect the market price. Suppose we knew that the share price of _Apple_, for example, was ```$100``` on Monday and by Wednesday it would be ```$200```. What would we have done? Everybody would want to ```buy``` on this perspective increase in price and nobody would be willing to ```sell```. 

The forecast of a future price increase would immediately lead to an increase in price ```today```. In other words, whatever the good news was that prompted us to believe that the price was going to increase would be immediately reflected into the price.

In more general terms, we can say that any ```information``` that could be use to predict future stock performance should already be reflected in the price today. That is, if there is any information that indicates that the stock is underpriced and offers a good opportunity, that investors would all flock to it, buy, and bid up the price, effectively incorporating the information into the price. 

But then if prices are immediately bid to fair levels, then they should only change in response to ```new information```. However, new information is, by definition, ```unpredictable``` (**entropy**). Therefore, stock prices that change in response to new information should also be ```unpredictable```.

**Note:**
This does not mean that the level of prices is ```irrational``` because the changes are ```unpredictable```. Instead, it means that if prices are determined ```rationally```, then the only reason they should change is for ```new information```. Only new information would cause them to change. The ability to predict prices, if there ever was an ability like that, would suggest that **not all available information** was already reflected in the prices.

- An efficient market is one that processes information efficiently, where prices reflect all available information. 
- The prices react quickly and correctly to the new information.
- If markets are efficient, then there is no _free lunch_. The only way to get ```higher returns``` is by taking on ```more risks```.

> To sum up, the Efficient Market Hypothesis states that prices should reflect all available information, or put differently, prices are **not predictable**, because they already reflect all available information.

#### 1.1.3 



#### 1.1.1 The three versions of EMH


<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168441894-6f4ff670-8d48-4c09-b398-1c5418ad6ffa.jpg" width="380" height="290"/>
</p>
<p align="center">
    “Don’t bother. If it was real, somebody else would’ve already picked it up.”
</p>
















__________________________________________________________________________ .. __________________________________________________________________________

#### 1.2 Random Walk Hypothesis (RWH)

__________________________________________________________________________ .. __________________________________________________________________________

#### 1.3 Are markets _really_ efficient?








------------------------

### 2. Understanding Time Series

#### 2.1 What are time series?



















<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/167879610-5d6285bc-cf74-41e3-99e1-8db24d809dfc.png" width="500" height="350"/>
</p>





## Further Improvements

## Conclusion

## References
1. https://people.duke.edu/~rnau/411rand.htm
2. https://towardsdatascience.com/how-to-detect-random-walk-and-white-noise-in-time-series-forecasting-bdb5bbd4ef81
3. https://www.investopedia.com/terms/r/randomwalktheory.asp#:~:text=Key%20Takeaways,to%20predict%20its%20future%20movement.
4. https://www.mit.edu/~kardar/teaching/projects/chemotaxis(AndreaSchmidt)/random.htm
5. https://people.duke.edu/~rnau/411diff.htm
6. https://www.investopedia.com/ask/answers/04/031104.asp
7. https://people.duke.edu/~rnau/411georw.htm
8. https://www.wsj.com/articles/SB109804865418747444
9. chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/http://www.econ.yale.edu/~shiller/pubs/p1055.pdf
10. https://knowledge.wharton.upenn.edu/article/is-that-a-100-bill-lying-on-the-ground-two-views-of-market-efficiency-2/
