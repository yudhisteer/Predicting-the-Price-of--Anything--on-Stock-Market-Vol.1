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

4. Exploratory Data Analysis and Static Analysis

    - QQ Plot
    - T-distribution
    - Confidence Intervals
    - Statistical Testing
    - Covariance and Correlation
    - Alpha and Beta
    - Gaussian Mixture Model

5. Exponential Smoothing and ETS Methods

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

#### 1.1.3 Proof of EMH
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


#### 1.1.4 The three versions of EMH
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

### 2. Financial Engineering: The Basics

#### 2.1 Financial Data

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 2.2 Returns

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 2.3 Adjusted close, stock splits and dividends

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 2.4 Volatility Clustering



------------------------

### 3. Understanding Time Series

#### 3.1 What are time series?

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 3.2 Statistics on time series

------------------------

### 4. Exploratory Data Analysis and Static Analysis

#### 4.1 QQ Plot

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 4.2 T-distribution

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 4.2 Confidence Intervals

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 4.2 Statistical Testing

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 4.2 Covariance and Correlation

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 4.2 Alpha and Beta

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 4.2 Gaussian Mixture Model

------------------------


### 5. Exponential Smoothing and ETS Methods

#### 5.1 Simple Moving Average (SMA)
A simple moving average (SMA) calculates the average of a selected range of data, usually closing prices, by the number of periods in that range. Since SMA is constructed using ```past``` closing prices, it is a ```lag``` indicator. It means that it simply displays a ```previous trend```, but it is ```not predictive``` of future prices.

- In code, we compute the SMA by taking the average of a **rolling window**.
- SMA is **equally weighted** since for a window of size ```n```, each point has a weight of ```1/n```.

The equation for the SMA is as follows:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168479663-2314aa8f-5485-4ba4-85d9-ea4511a2240b.png"/>
</p>

where:

- <img src="https://latex.codecogs.com/png.image?\dpi{110}x_{n}" title="https://latex.codecogs.com/png.image?\dpi{110}x_{n}" /> is the price of an asset at period n
- n is the total number of periods or the size of the rolling window.

In the example below, a 3-day moving average would average out the closing prices for the first 3 days as the first data point. The first data points are ```2```, ```1``` and ```6``` and the average of these 3 data points are ```3``` which is placed at the third index of the time series. Notice that the first two indexes are null as our rolling window is ```3``` and there are no ```3``` data points before the first and second data points. We then move our rolling window one step to the right and compute the average of ```1```, ```6``` and ```8``` which becomes ```5``` and we continue as such. 


<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168477297-7efc63db-7166-4f4d-b307-c32902170fd6.png" width="450" height="210"/>
</p>


The purpose of the simple moving average is to ```smooth out``` **volatility** and makes it easier to view the price ```trend``` of a stock. If the simple moving average points up, this means that the security's price is increasing. If it is pointing down, it means that the security's price is decreasing. 

> The ```longer``` the time frame for the moving average, the ```smoother``` the simple moving average. A ```shorter-term``` moving average is more ```volatile```, but its reading is closer to the ```source``` data.

In the figure below, note that ```short-term``` averages (10-day SMA) respond ```quickly``` to changes in the price of the underlying security, while ```long-term``` averages (50-day SMA) are ```slower``` to react. 

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168479920-f6cd0676-4843-4fb3-b257-687c1ab82c64.png" />
</p>

```python
#import data
df = pd.read_csv(filepath, index_col = 0, parse_dates=True)
goog = df[['GOOG']].copy().dropna() #delete empty rows

#calculate log returns
goog_ret = np.log(goog.pct_change(1)+1)

#calculate 10-day and 50-day SMA
goog['SMA-10'] = goog['GOOG'].rolling(10).mean()
goog['SMA-50'] = goog['GOOG'].rolling(50).mean()
```

#### 5.1.1 How Are Simple Moving Averages Used in Technical Analysis?

```SMA crossover strategy``` is a technical strategy used for entering and closing trades. The strategy is done by plotting two SMA lines based on two different time frames. Looking at when the lines cross over, helps certain traders time their trades. The most famous are the 10-day and 200-day SMAs. For our analysis, we did the 10-day and 50-day SMAs. 

When the 10-day line (**orange**) first crossed **above** the 50-day line (**green**) (```2015-02```), the ```golden cross```, indicates potential for a market rally. An investor who bought the stock would ideally capitalize on a an ```upwards trend```. If the investor sold it right when the 10-day line crossed **under** the 50-day line (```2014-10``` and ```2015-04```), the ```death cross``` which is considered a bearish signal, indicating that further losses are in store, they would’ve exited their position before a couple of months of an overall ```downtrend```.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168483806-30022bf8-9f28-4b89-9af5-4eed2811de05.png" />
</p>

To sum up:

- When analysing stock prices we are not sure whether we should put more emphasis on current or past data. While some believe that new data will provide a better trend pattern of the stock, other feel that taking into account only certain data points introduces biasness. Recall that with SMA we treat the 10th or the 50th data point with the same weightage. 
 
- Not to forget that the Efficient Market Hypothesis states that prices already reflect all available information. Then if markets are indeed efficient, using historical data should tell us nothing about the future direction of asset prices.


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 5.2 Exponentially Weighted Moving Average (EWMA)
While a simple moving average gives equal weight to each of the values within a time period, an exponential moving average places greater weight on recent prices. Exponential moving averages are typically seen as a more timely indicator of a price trend, and because of this, many traders prefer using this over a simple moving average. 

At each step, the moving average is the weighted sum of the new sample and the old moving average. The formula for EWMA is as follows:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168573226-0ccc7c79-8ed0-4fc9-a271-21a79c282a78.png"/>
</p>


where:

- <img src="https://latex.codecogs.com/png.image?\dpi{110}\bar{x}_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}\bar{x}_{t}" /> is the moving average at time t
- <img src="https://latex.codecogs.com/png.image?\dpi{110}\bar{x}_{t-1}" title="https://latex.codecogs.com/png.image?\dpi{110}\bar{x}_{t-1}" /> is the previous moving average
- <img src="https://latex.codecogs.com/png.image?\dpi{110}{x}_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}{x}_{t}" /> is the current data point
- <img src="https://latex.codecogs.com/png.image?\dpi{110}\beta" title="https://latex.codecogs.com/png.image?\dpi{110}\beta" /> is the smoothing parameter between 0 and 1.


Note that as <img src="https://latex.codecogs.com/png.image?\dpi{110}\beta" title="https://latex.codecogs.com/png.image?\dpi{110}\beta" /> increases, we get a smoother time series. We can think of <img src="https://latex.codecogs.com/png.image?\dpi{110}\bar{x}_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}\bar{x}_{t}" /> as averaging over <img src="https://latex.codecogs.com/png.image?\dpi{110}\frac{1}{1-\beta&space;}" title="https://latex.codecogs.com/png.image?\dpi{110}\frac{1}{1-\beta }" /> days' of data points. 

- <img src="https://latex.codecogs.com/png.image?\dpi{110}\beta=0.9\to&space;&space;" title="https://latex.codecogs.com/png.image?\dpi{110}\beta=0.9\to " /> averaging over ```10``` days' of data points
- <img src="https://latex.codecogs.com/png.image?\dpi{110}\beta=0.98\to&space;&space;" title="https://latex.codecogs.com/png.image?\dpi{110}\beta=0.98\to " /> averaging over ```50``` days' of data points.

Notice how with beta equal to ```0.1``` our moving average time series is very close to the actual data points. The exponentially weighted average is as nosiy as the real data. But as we increase beta, we get smoother graphs. With beta equal to ```0.9``` we get a nice smoothe time series and with beta = ```0.98```, we get a too smooth time series.

![image](https://user-images.githubusercontent.com/59663734/168596902-373141e4-94bc-4c4b-ae52-dbecd4b5cbb7.png)

This is why we get a smoother graph with bigger <img src="https://latex.codecogs.com/png.image?\dpi{110}\beta" title="https://latex.codecogs.com/png.image?\dpi{110}\beta" /> as we are averaging over more days. We are actually giving more weightage to <img src="https://latex.codecogs.com/png.image?\dpi{110}\frac{1}{1-\beta}" title="https://latex.codecogs.com/png.image?\dpi{110}\frac{1}{1-\beta}" /> days. But the drawback is that the curve has now been shifted to the right, that is, we have more ```latency```. By averaging over a large window, the EWMA adapts more slowly to changes in the share prices. 

#### 5.2.1 Deriving the equation
How do we find the moving average? We normally initalize <img src="https://latex.codecogs.com/svg.image?\bar{x}_{0}=0" title="https://latex.codecogs.com/svg.image?\bar{x}_{0}=0" />:


<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168577961-232d2170-e592-4423-b556-39ff98839b51.png"/>
</p>

Notice that <img src="https://latex.codecogs.com/svg.image?\beta&space;\cdot&space;\bar{x}_{0}=0" title="https://latex.codecogs.com/svg.image?\beta \cdot \bar{x}_{0}=0" />  as <img src="https://latex.codecogs.com/svg.image?\bar{x}_{0}=0" title="https://latex.codecogs.com/svg.image?\bar{x}_{0}=0" />. When expanding:


<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168579582-8ddabf1d-e881-496c-a37b-89b6b76a58d8.png"/>
</p>

As we move forward in time, the power of <img src="https://latex.codecogs.com/svg.image?\beta&space;" title="https://latex.codecogs.com/svg.image?\beta " /> will increase for the older terms while the power of <img src="https://latex.codecogs.com/svg.image?\beta&space;" title="https://latex.codecogs.com/svg.image?\beta " /> will be less for newer data points. That is older data points get less weightage than newer data points. 



#### 5.2.2 Choosing Beta

We normally chosse <img src="https://latex.codecogs.com/svg.image?\beta&space;" title="https://latex.codecogs.com/svg.image?\beta " /> to be ```0.9```. With this value  we are actually averaging over ```10``` days which does not have too much **latency** and too much **noise**. 

- <img src="https://latex.codecogs.com/svg.image?\beta&space;=&space;1&space;" title="https://latex.codecogs.com/svg.image?\beta = 1 " />

Our formula is reduced to:


<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168584102-1b445e9a-156e-43c8-adec-769dd40a9d9e.png"/>
</p>

That is, the current moving average is equal to the previous moving average and we get a very smooth line (a horizontal line).

- <img src="https://latex.codecogs.com/svg.image?\beta&space;=&space;0" title="https://latex.codecogs.com/svg.image?\beta = 0" />

Our formula is reduced to:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168584369-3535eb96-00d5-4ec0-ac77-6e4a9f0bee80.png"/>
</p>

The moving average is just equal to the current data point. So we only have the existing time series graph and no other line for the moving average.

Notice how with beta = ```0```, our time series is exactly the actual data points. This is because when beta equal to zero, our moving average is the current data point so we get another graph overlayed on our actual data points. With beta equal to ```1```, we get a horizontal line which is equal to the first value in our time series (<img src="https://latex.codecogs.com/png.image?\dpi{110}y&space;=&space;x_{0}" title="https://latex.codecogs.com/png.image?\dpi{110}y = x_{0}" />). This is because when beta equal to ```1```, our moving average is equal to the previosu average. But since our previous average is always constant then our moving average remains constant (<img src="https://latex.codecogs.com/png.image?\dpi{110}\bar{x}&space;=&space;n\cdot&space;x&space;/&space;x" title="https://latex.codecogs.com/png.image?\dpi{110}\bar{x} = n\cdot x / x" />). 

![image](https://user-images.githubusercontent.com/59663734/168596225-081773db-45ac-41a1-86b1-22699748c132.png)

Hence, a better value for beta is equal to ```0.9``` as shown above.

To sum up: 

-  Recall that with SMA each term is given an **equal weight**. This problem is fixed by using the exponentially weighted moving average (EWMA), in which more recent returns have greater weight compared to older ones.

- With EWMA the weight decays **exponentially** going backwards in time. This means the latest sample matters the most, the second sample matters less and the thirds one matters even less and so forth.

- The EWMA is a **recursive** function, which means that the current observation is calculated using the previous observation. The only decision a user of the EWMA must make is the parameter ```beta```. The parameter decides how important the current observation is in the calculation of the EWMA.

- The EWMA can also be used in a **simple crossover strategy**, where a buy signal is generated when the price crosses the EWMA from above, and a sell signal is generated when the price crosses the EWMA from below. (Same as we have seen with SMA where we have used a 10-day SMA and a 50-day SMA to analyze when is the most appropriate time to buy and sell.)

The EWMA at time ```t``` can also be expressed as the previous EWMA:

    
<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168609968-4b53ea69-6f7a-4476-8d73-ddc60b8a6360.png"/>
</p>


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 5.3 Simple Exponential Smoothing (SES)

With Simple Exponential smoothing (SES), we are going to bridge the gap between **exponential smoothing** and the **Holt-Winters model**. Previously we only calculated the different ways we can take the average in a time series, but now we want to know how we can fit a model to the series and use that model for ```forecasting```. For that, we need to understand exponential smoothing in the perspective of time series forecasting. 

- We will turn our EWMA into a **forecasting** model.
- This assumes tha tour time series fluctuate around some **constant** value in time.
- The model will try to **learn** what this average value is by using the EWMA.
- In order to forecast beyond the data, it simply assumes the final EWMA value will **propagate** into the future.
- The logic holds according to the assumption of the model that the times series has a **constant value** **+** **random noise** whereby our constant value is the ```level```.

Recall that our Exponentially Weighted Moving Average (EWMA) is in the form of:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168738329-629eab79-8e2a-4d52-a746-fc1501331944.png"/>
</p>

We will slightly modify our equation using <img src="https://latex.codecogs.com/png.image?\dpi{110}\alpha&space;" title="https://latex.codecogs.com/png.image?\dpi{110}\alpha " /> such that <img src="https://latex.codecogs.com/png.image?\small&space;\dpi{110}1-&space;\beta&space;=&space;\alpha&space;" title="https://latex.codecogs.com/png.image?\small \dpi{110}1- \beta = \alpha " />:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168738026-49f90248-4625-4489-8cee-3487b9a54bde.png"/>
</p>

With new notation the equation becomes:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168738635-26df4716-a764-436e-8f0d-51eeb1ab9241.png"/>
</p>

where:

- <img src="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t}" /> is the exponentially smoothed version of y at times t.
- <img src="https://latex.codecogs.com/png.image?\dpi{110}y" title="https://latex.codecogs.com/png.image?\dpi{110}y" /> is the value from the time series as time t
- <img src="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t-1}" title="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t-1}" /> is the previous exponentially smoothed y at time t-1
- <img src="https://latex.codecogs.com/png.image?\dpi{110}\alpha&space;" title="https://latex.codecogs.com/png.image?\dpi{110}\alpha " /> is the smoothing parameter between 0 and 1

We wil now phrase the equation as a forecasting model:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168742419-c50c4db6-57eb-4060-9711-3c959f833140.png"/>
</p>

where:

- <img src="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t&plus;1|t}" title="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t+1|t}" /> is the exponential smoothed forecast for time t + 1 given known value at time t.
- <img src="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t|t-1}" title="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}_{t|t-1}" /> is the previous exponentially smoothed value
- <img src="https://latex.codecogs.com/png.image?\dpi{110}y_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}y_{t}" /> is the current value at time t

Previously we were just averaging our time series model but now we are forecasting for the next time step. The equation above can simply be written as:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168743529-6edd9bdf-e34e-4b2a-a532-79625b86a140.png"/>
</p>

Below we plot the EWMA and SES on an Airline dataset which clearly shows a trend and seasonality. We choose alpha to be ```0.7``` and we immediately notice a discrepancy in the graph of SES and EWMA. This is because our forecasting model is defined slightly different from a EWMA. Recall that the forecasting time index is move up by one step and the EWMA is represented by the level. The prediction <img src="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}" title="https://latex.codecogs.com/png.image?\dpi{110}\hat{y}" /> is actually assigned to the level at the previous time step. In other words, the SES should in fact be lagging behind the EWMA by one time step.

![image](https://user-images.githubusercontent.com/59663734/168778115-12a5e173-8e70-49ca-ab31-96879a78daf9.png)

```python
df = pd.read_csv(filepath, index_col = 0, parse_dates=True)
df.index.freq = 'MS'

#create instance of SES
ses = SimpleExpSmoothing(df['Passengers'])

#fit SES to data
alpha = 0.7
res = ses.fit(smoothing_level=alpha, optimized=False)

#calculate EWMA on data
alpha = 0.7
goog['EWMA'] = goog['GOOG'].ewm(alpha=alpha, adjust=False).mean()
```


#### 5.3.1 Component Form
We will now express our Simple Exponential Smoothing model into component form. When we will see the Holt-Winters model which consists of multiple components then this decomposition will become more useful.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168746023-813b9237-c757-4cb1-9e7d-06f2dfd57ca4.png"/>
</p>

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168746430-6a87a4aa-eecf-4212-97d2-851ab4423cec.png"/>
</p>

Notice how our Smoothing Equation is just the Exponentially Moving Average and the Forecast Equation is the forecast at an arbitrary ```h``` steps ahead. <img src="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" />  is it self not a forecast but the forecas tis based on <img src="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" />. For this simple mode, the forecast is simply assigned to be <img src="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" /> but this will be more complex later on.

<img src="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" /> is called the ```level``` which can be though as the **moving average**. The level is the average value of the signal in time but the actual signal may fluctuate around  that average level. Note that the forecast is just a constant value - <img src="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}l_{t}" /> - no matter how many steps ahead we want to forecast. This is the case because the EWMA is nothing but the mean. Since our estimate is the mean, that's the only thing we can predict. After we stop collecting data, we have no idea how this mean will change beyond the last known data point. And so our forecast simply consists of predicting the last known value for each time step. 

Below I just used the ```fit``` method for the model to choose the optimized alpha value on the Google Stock price dataset. The reason why we would not choose stock price for prediction is because we need to assign ```df.index.freq``` first to our dataframe which is clearly in days. Alas, our dataset does not have values for Saturdays and Sundays hence, this creates an error when forecasting. We would need a constant time interval dataset and that is why we choose the Airline Passengers dataset for prediction.

```python
ses = SimpleExpSmoothing(train['GOOG']) 
res = ses.fit() #function finds best alpha by minimizing squared error over training set
```
We get the optimized alpha value to be ```0.9999999850988388``` using ```res.params```.

```python
{'smoothing_level': 0.9999999850988388,
 'smoothing_trend': nan,
 'smoothing_seasonal': nan,
 'damping_trend': nan,
 'initial_level': 558.4600000236849,
 'initial_trend': nan,
 'initial_seasons': array([], dtype=float64),
 'use_boxcox': False,
 'lamda': None,
 'remove_bias': False}
```


![image](https://user-images.githubusercontent.com/59663734/168778201-624b5e45-ad47-4a99-95d8-bf9c037fd8f0.png)

![image](https://user-images.githubusercontent.com/59663734/168783319-c86c5631-2cc7-4766-8268-ad096e70047b.png)


To sum up:

- Simple Exponential Smoothing, is a time series forecasting method for univariate data without a trend or seasonality.

- The basic idea of this model is to assume that the future will be more or less the **same** as the (recent) past. Thus, the only pattern that this model will learn from demand history is its **level**.

-  Large values of alpha mean that the model pays attention mainly to the most recent past observations, whereas smaller values mean more of the history is taken into account when making a prediction.

- Our focecast depend on the level which is a constant value after our last known data point.








<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 5.4 Holt's Linear Trend Model

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 5.5 Holt-Winters Model

------------------------


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
13. https://www.investopedia.com/terms/s/sma.asp#:~:text=A%20simple%20moving%20average%20smooths,the%20security's%20price%20is%20decreasing
14. https://corporatefinanceinstitute.com/resources/knowledge/trading-investing/simple-moving-average-sma/
15. https://www.investopedia.com/terms/d/deathcross.asp
16. https://towardsdatascience.com/simple-exponential-smoothing-749fc5631bed
17. https://machinelearningmastery.com/exponential-smoothing-for-time-series-forecasting-in-python
