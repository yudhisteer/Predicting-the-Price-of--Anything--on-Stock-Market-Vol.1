# Predicting the Price of "Anything" on Stock Market



## Abstract


## Research Questions

## Methods

## Plan of Action

1. Behavioral Economics: Ways people or markets misbehave

    - Efficient Market Hypothesis (EMH)
    - Random Walk Hypothesis (RWH)
    - Are markets efficient?
    - Biases and Heuristics
    - Inefficient Markets
    - Irrational Behavior

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
#### 1.1.1 History of EMH
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

- An efficient market is one that processes information **efficiently**, where prices reflect **all** available information. 
- The prices react **quickly** and **correctly** to the new information.
- If markets are efficient, then there is no _free lunch_. The only way to get ```higher returns``` is by taking on ```more risks```.

> To sum up, the Efficient Market Hypothesis states that prices should reflect all available information, or put differently, prices are **not predictable**, because they already reflect all available information.

#### 1.1.4 Proof of EMH
Recall the efficient market hypothesis states that in an efficient market, prices are unpredictable because they already reflect all available information.
And they change only when new information arrives by reacting very quickly to reflect the new information.

Nokia shares weren’t looking good since October 2019, but their price suddenly improved in a single afternoon. Rumors about Nokia takeover caused share prices to surge. In takeover cases the acquiring firm pays a substantial premium over the current market price. Therefore the announcement of a takeover should cause the market price to increase. 

The plot shows that the prices, due to the rumor of a takeover, had a sudden increase in share price of Nokia after a report posted by Bloomberg, but after an opposing report was posted by Reuters, the stock price went back down.

![sketchpad pro_E81FCB94AEA47906C98](https://user-images.githubusercontent.com/59663734/168446385-da6acc90-1db9-499a-ac40-8a4d3a738718.png)

> Bloomberg’s report citied a source inside Nokia with knowledge that the company is exploring strategic options like sales, acquisitions and mergers to better compete in the network infrastructure business. The report even mentioned a merger with Ericsson, one of Nokia’s two main competitors. Shortly after, Reuters published a report in which their source close to Nokia denies everything Bloomberg posted.
> 
So we can see that this is very consistent with the idea that prices reflect the new information, the announcement of a takeover attempt or debugging the rumors, very quickly.

An even more impressive example comes from a study - "**Market efficiency in real time**" - that tracked minute by minute stock prices of firms that were featured on CNBC's morning or mid-day segments. In the graph below the minute ```0``` indicates the time at which the stock was mentioned in the show. The ```green line``` corresponds to the average price movement of stocks that received ```positive``` reports and the ```red line``` shows the returns on stocks that received ```bad``` reports.

Notice also that the green line levels off after about ```5``` minutes after the report, that is, the market fully digests that news within about 5 minutes. In contrast, the red line takes a little longer. The negative news driffs down until about ```10``` minutes after it is measured.
<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168456915-6c2c87cd-1418-4beb-a79a-3458b60c412b.png" width="900" height="350"/>
</p>

And to see this impressive effect in real-time, below we have a video of a real time market reaction to a CNBC mid-day call which supports the Market Efficiency Hypothesis.

https://user-images.githubusercontent.com/59663734/168446780-b2927add-3814-4c2e-821b-cbf2054844ac.mp4


#### 1.1.1 The three versions of EMH
We have been talking about how EMH is dependent on information but what is all this "information". Information in itself is pretty broad. It is comprised of pretty much everything in the world. Note that investing is a large-scale engineering problem and not just a data science problem. To be more concrete, we can categorize "information" in 4 types:

- Technical data: price, volume,...
- Fubdamentals data: quarterly reports
- Exogenous data: Facebook, Twitter, news,...
- Insider information: non-public data

So when we say that the Efficient Market Hypothesis states that prices should reflect all available information, these are the 4 types of information we are talking about. The amount of informaiton described above can be quite intimidating and coming to think about it, it now really seem to be impossible to make any prediction on the return of a stock as the volume of data needed is humongous and not always publicly available. 

We will now discuss the 3 forms of efficient market hypothesis and the different implications for what we can expect to see in the markets. The types are:

**1. Weak**

The weak form of the efficient market hypothesis states that:
- prices reflect all **marketing data** - ```past prices```, ```trading volume```, or ```short interests```. 
- we **can't predict future prices** by looking at past prices or past volume.
- **trend analysis** is completely useless - future performance has no relationship with past performance. 
- we cannot use **technical analysis** to predict returns.

If markets are weak form efficient, we can't use any past trading data, price or volume data, that is publicly available and virtually costless to obtain to predict future stock prices or future performance. And if such data were able to predict future prices, then all investors would have **already** exploited those signals, and therefore that information would **already** be reflected in the prices.

**2. Semi-strong**

The semi-strong form of the efficient market hypothesis states that:
- all **publicly available information** should already be reflected in prices - on top of the marketing data we now have accounting data, financial data, fundamental data, patents, product line, earnings forecast...
- even with technical and fundamental data, we will cannot beat the market.

The only way we can reap benefits with fundamental analysis is if our analysis is better than our competitor. And how could it be better? Is it better understanding of the fundamentals, or is it private information?

**3. Strong**

The strong form of the efficient market hypothesis states that:
- Even with all information available - public and private - we still cannot beat the market! That is, prices reflect all available information - public and even including information that is only available to insiders. 


Undoubtedly, company insiders are likely to have valuable information that is not public and that will allow them to profit from their information. The SEC in the US tries to prevent exactly this kind of situation where insiders can exploit their private information to profit. The SEC regulates the trading activity of company insiders by requiring them to report their trades to the SEC.


So far it appears that efforts to pick stocks by predicting future prices is not very useful as competition among investors is likely to ensure that any useful information will already be reflected in market prices. So what can we do in this situation?

> The efficient market hypothesis would suggest that a ```passive investment strategy``` (to invest in an index fund: S&P 500), one that makes no effort to beat the markets but merely aim at establishing a large well ```diversified portfolio``` securities, without trying to find undervalued or over valued stocks. This is because the efficient market hypothesis indicates that prices are already at their fair value given all the available information. Therefore it makes no sense to try to buy or sell individual securities. 

Below is the famous $20 bill joke on the EMH. Tomorrow if you find a bank note on the sidewalk, before picking it up, ask yourself if it was really a bank note, then shouldn't someone before me already have picked it up?

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168441894-6f4ff670-8d48-4c09-b398-1c5418ad6ffa.jpg" width="380" height="290"/>
</p>
<p align="center">
    “Don’t bother. If it was real, somebody else would’ve already picked it up.”
</p>

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 1.2 Random Walk Hypothesis (RWH)


![rand_2D](https://user-images.githubusercontent.com/59663734/168471883-1f124262-bcba-4d95-bac4-da51fac10640.gif)









<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 1.3 Are markets _really_ efficient?



<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 1.4 Biases and Heuristics

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 1.5 Inefficient Markets


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 1.6 Irrational Behavior


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
9. http://www.econ.yale.edu/~shiller/pubs/p1055.pdf
10. https://knowledge.wharton.upenn.edu/article/is-that-a-100-bill-lying-on-the-ground-two-views-of-market-efficiency-2/
11. https://nokiamob.net/2020/04/17/rumors-about-nokia-hostile-takeover-causes-stock-price-surge/
12. https://nokiamob.net/2020/02/27/bloomberg-and-reuters-post-conflicting-reports-about-nokia-exploring-strategic-options/
