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


3. Exploratory Data Analysis and Static Analysis

    - What are time series?
    - Objectives of time series
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

5. Time Series Analysis

    - Deterministic Dependencies: Trend and Seasonality
    - Stochastic Dependence
    - Stationarity
    - Transformation towards Stationarity
    - Diagnosing Stationarity with Autocorrelation Function (ACF)

5. Statistical Models

    - White Noise Model
    - Random Walk Model
    - ARIMA Model
    - ACF and PACF
    - Auto ARIMA
    - VARMA

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


### 3. Exploratory Data Analysis and Static Analysis

#### 3.1 What are time series?
Time series is a special kind of statistical data, specifically, it is a **collection of observations of random variables** <img src="https://latex.codecogs.com/svg.image?x_{1},...,x_{n}" title="https://latex.codecogs.com/svg.image?x_{1},...,x_{n}" /> indexed by a **fixed time intervals**. 


For example, if I take ```temperature``` every day, all these data will be my **measurements**. They are not independent and they would be my observations indexed by the day. Let's say I have a random variable for each day and that is the temperature in each day. So our **observations are just realizations of these random variables**. The ```challenge``` is that we only have **one observation** for each of these variables because we have only one measurement for each day. More generally, the probability model is such that we have one random variable for each time stamp and one observation for each random variable. 

Below, we have some real-world time series and we can see how each of them differ from each other. We will later explore terms like ```trend``` and ```seasonality``` in depth. 

![image](https://user-images.githubusercontent.com/59663734/170647202-4502c4d5-15a9-430c-aab0-e2e49699247d.png)

Based on the obeservations above, we see  ```2``` difference between the time series:

- ```Components```
    - We can **decompose** a time series such that the value at time ```t``` is equal to the ```trend```, the ```seasonality``` and the ```noise```. Note that some of the time series have a trend and some have a seasonaity while some don't.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170649163-471f4ae7-e474-4f8a-a238-e24f095de11c.png"/>
</p>

- ```Smoothness```
     - We also observe how some time series is ```smooth``` over time and some are very ```heractic```. The smoothness can be quantified by a **correlation in time**, i.e, values that are fairly ```close``` to each other, they tend to be also pretty similar. so for a smooth time series, we have a large correlation in time and for a heractic one, we have less correlation in time. 

> Time series is a collection of realizations of distinct random variables (i.e. a different random variable at each time index) at equally spaced points in time.


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 3.3 Objectives of Time Series
Now, why would we want to study time series and what can we learn from it? On a higher level, we want to study time series for the ```5``` reasons below:

- **Descriptive Analysis**
     - We may want to analyze in words, just like we did above, the time series. We may also want to analyze the ```components```, i.e, how the trend is changing over time, if we have a seasonality or not. We may also want to understand the ```relationship``` between several time series, understanding the ```dependencies```, ```correlation``` or whether it is ```smooth``` or not. 

- **Modeling**
    - We may also want to fit a ```statistical model``` to have a compact description of the time series to further enhance our understanding of the time series. 

- **Forecasting**
    - We may use the statistical model to do forecasting that can help us make better ```business decisions```.

- **Time Series Regression**
    - We may use time series regression to predict values of one time series by using values of the same time series or other time series in the past. So we may want to predict one time series as a function of others or the same time series. Note that this is a little bit more complicated than normal regression because in regression we typically assume that our data is ```IID```.

 - **Control**
    - We may also use time series for control of other parameters. For example, the steering angle of a car based on the forecasting of a specific time series.


From a statistical point of view, we want to study time series to understand and exploit the **deterministic** and **stochastic** dependencies of the stochastic process that generated the data. Specifically, we want to develop statistical tools and models to

- **Detect the trend**

- **Detect seasonal variation and determine its period length**

- **Understand the correlation structure within the same time series**

- **Understand the correlation structure between two different time series**

As  mentioned above, one of the main objective is to ```forecast``` future observations of the series. This requires **estimating** the ```trend``` and the ```seasonal``` component and fitting a ```statistical model``` that captures the ```correlation structure``` between adjacent observations. We can then form a ```prediction``` of the future from the past by extrapolating on all the ```dependencies``` in the series that we learn from data with statistics. In some applications of time series these dependence properties are of interest on their own.













<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 3.1 QQ Plot

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 3.2 T-distribution

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 3.2 Confidence Intervals

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

Below I used the ```fit``` method for the model to choose the optimized alpha value on the Google Stock price dataset. We see that although we have a very high value of alpha, we can still see some discrepancy in the predicted values (although it is shifted by one time step) mainly due to the noise in our data.

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

The reason why we would not choose stock price for prediction is because we need to assign ```df.index.freq``` first to our dataframe which is clearly in days. Alas, our dataset does not have values for Saturdays and Sundays hence, this creates an error when forecasting. We would need a constant time interval dataset and that is why we choose the Airline Passengers dataset for prediction.
 
We will split our dataset manually such that we would want the model to predict the last ```12``` data points. We then call ```model.fit``` with no alpha value assigned. We apply ```fittedvalues``` on our training set and ```forecast()``` on our test set. 

```python
N_test = 12
train = df.iloc[:-N_test]
test = df.iloc[-N_test:]

ses = SimpleExpSmoothing(train['Passengers'], initialization_method='legacy-heuristic')
res = ses.fit()

#create boolean values for train and test
train_idx = df.index <= train.index[-1]
test_idx = df.index > train.index[-1]

df.loc[train_idx, 'SESfitted_Train'] = res.fittedvalues
df.loc[test_idx, 'SESfitted_Test'] = res.forecast(N_test)
```
On this dataset, the optimized alpha value is ```0.995```.  

```python
{'smoothing_level': 0.995,
 'smoothing_trend': nan,
 'smoothing_seasonal': nan,
 'damping_trend': nan,
 'initial_level': 112.0,
 'initial_trend': nan,
 'initial_seasons': array([], dtype=float64),
 'use_boxcox': False,
 'lamda': None,
 'remove_bias': False}
```
As we can see the forecast is indeed a horizontal straight line. Note that for the training set, the prediction looks that it is lagging behind by one step which is perfectly correct as the prediction is the level value at the previous time step. For the fitted alpha of ```0.995``` we can see that the model is reacting very quickly to the original time series which indicates that it cares more about the most recent sample than the previous average.

![image](https://user-images.githubusercontent.com/59663734/168783319-c86c5631-2cc7-4766-8268-ad096e70047b.png)

Figure below shows the last 15 values in our dataset whereby the prediction values remain constant at the level value of ```404.786132```.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/168789887-933f32b9-df75-4fb6-8798-717996e53e70.png" width="350" height="350"/>
</p>



To sum up:

- Simple Exponential Smoothing, is a time series forecasting method for univariate data without a trend or seasonality.

- The basic idea of this model is to assume that the future will be more or less the **same** as the (recent) past. Thus, the only pattern that this model will learn from demand history is its **level**.

-  Large values of alpha mean that the model pays attention mainly to the most recent past observations, whereas smaller values mean more of the history is taken into account when making a prediction.

- Our focecast depends on the level which remains a constant value after our last known data point.

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 5.4 Holt's Linear Trend Model
Recall from the example above how the forecast with our SES model was always a horizontal line. This is because we were only computing the level which is the average of our time series and our forecast was equal to the previous level value. However, in time series data we happen to have a trend and seasonality also. Hence, in this section we will implement a component for ```trend``` which will allow us to model trends, that is, to have lines(our forecast) at any angle.

We will first model the equations in component form:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/169801477-4db5fa6a-d1a5-4130-8da5-1a1a80cf827d.png"/>
</p>

- Notice that our **level** equation has been modified to implement the **previous trend value**. We update the level using <img src="https://latex.codecogs.com/svg.image?l_{t-1}&space;&plus;&space;b_{t-1}&space;=&space;l_{t-1}&space;&plus;&space;1\cdot&space;&space;b_{t-1}" title="https://latex.codecogs.com/svg.image?l_{t-1} + b_{t-1} = l_{t-1} + 1\cdot b_{t-1}" /> where h = 1 represents one step increase due to trend. It is still exponential smoothing on the input signal using <img src="https://latex.codecogs.com/svg.image?l_{t-1}" title="https://latex.codecogs.com/svg.image?l_{t-1}" /> and <img src="https://latex.codecogs.com/svg.image?b_{t-1}" title="https://latex.codecogs.com/svg.image?b_{t-1}" /> as the previous smoothing value.

- For our **trend** equation, notice that <img src="https://latex.codecogs.com/svg.image?l_{t}&space;-&space;l_{t-1}" title="https://latex.codecogs.com/svg.image?l_{t} - l_{t-1}" /> is the ```slope``` of the signal in one step where the latter expression is actually divided by ```1```(```1``` is the time difference). <img src="https://latex.codecogs.com/svg.image?b_{t}" title="https://latex.codecogs.com/svg.image?b_{t}" /> is also an exponentially estimate, that is, it is trying to estimate the slope or trend of the signal. The reason we use <img src="https://latex.codecogs.com/svg.image?l_{t}" title="https://latex.codecogs.com/svg.image?l_{t}" /> and not <img src="https://latex.codecogs.com/svg.image?y_{t}" title="https://latex.codecogs.com/svg.image?y_{t}" /> is because our time series data is noisy. So the level represents a smooth version of that signal without the noise. Therefore, taking the difference in <img src="https://latex.codecogs.com/svg.image?l_{t}" title="https://latex.codecogs.com/svg.image?l_{t}" /> represents a better estimate on the overall trend because it essentially removes that noise from the equation.

- The **forecast** equation is now made up of ```2``` components: ```level``` and ```trend```. Notice that <img src="https://latex.codecogs.com/svg.image?l_{t}" title="https://latex.codecogs.com/svg.image?l_{t}" /> is the starting value and y-intercept of the equation. <img src="https://latex.codecogs.com/svg.image?b_{t}" title="https://latex.codecogs.com/svg.image?b_{t}" /> is the slope of the equation with ```h``` is equal to the number of steps in the future. The forecast increases/decreases by the amount <img src="https://latex.codecogs.com/svg.image?b_{t}" title="https://latex.codecogs.com/svg.image?b_{t}" /> for each step in the future that we forecast. Our forecast is no longer a horizontal line but a line in any direction, hence, has the form of <img src="https://latex.codecogs.com/svg.image?y&space;=&space;m\cdot&space;x&space;&plus;&space;b" title="https://latex.codecogs.com/svg.image?y = m\cdot x + b" />.

The question that we should now ask is how do we choose ```alpha``` and ```beta``` in the above equations? It turns how these variables will no longer be chosen by us but rather the Scikit-learn library will fit them to our in-sample data by minimizing a loss function using gradient descent. 

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/169805714-d351b246-c444-4b67-b4ac-76b47d3a9414.png"/>
</p>

We will now implement the Holt's Linear Trend Model in our Airline Passengers dataset and observe how this is a better estimate that our SES model.

```python
from statsmodels.tsa.holtwinters import Holt
holt = Holt(df['Passengers'], initialization_method='legacy-heuristic')

res_h = holt.fit() #we no longer choose alpha and beta
df.loc[train_idx, 'Holt'] = res_h.fittedvalues
df.loc[test_idx, 'Holt'] = res_h.forecast(N_test)  
```

![image](https://user-images.githubusercontent.com/59663734/169806612-51aa5471-c5e9-4b4e-a814-569641dacc20.png)

As expected, we get a straight line trending upwards which is exactly what the Holt's Linear Trend model should be doing in this scenario.

<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 5.5 Holt-Winters Model
So far we have seen the ```Simple Moving Average (SMA)```, ```Exponentially Weighted Moving Average (EWMA)```, ```Simple Exponential Smoothing``` as a forecasting model and the ```Holt's Linear Trend``` model which added a trend component. Now we will explore the Holt-Winters model which extends the Holt's Linear Trend by  adding a **seasonal** component.

> Seasonality is a characteristic of a time series in which the data experiences ```regular``` and ```predictable``` changes that **recur** every calendar year.  Any predictable fluctuation or pattern that recurs or repeats over a one-year period is said to be seasonal.

Many time series data has a seasonal pattern such as weather, air conditioner sales, swimsuits sales and so on. For these kind of time series, there are generally ```3``` components: level (average), (linear) trend and seasonal (cycles). When combined together, we get our full time series data. There are ```2``` ways of doing this:

- **Additive**: ```y = level + trend + seasonal```
- **Multiplicative**: ```y = (level + trend) x seasonal```

#### 5.5.1 Additive Model
In the additive model, the seasonal component is added to the trend and level. A noisy line is added to some periodic signal and this periodic signal being periodic does not change over time. 

The equations in component form:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/169821436-f87d722e-8d64-41b4-afd3-7ab2ce29cca8.png"/>
</p>

- The **forecast** equation being the center-piece combines all teh components to give us a full output. We still have our Holt's Linear Trend model (<img src="https://latex.codecogs.com/png.image?\dpi{110}l_{t}&space;&plus;&space;h\cdot&space;b_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}l_{t} + h\cdot b_{t}" />) but now we have <img src="https://latex.codecogs.com/png.image?\dpi{110}s_{t&plus;h-mk}" title="https://latex.codecogs.com/png.image?\dpi{110}s_{t+h-mk}" /> added to it. 

    - **m**: period of a cycle. Period in physics is refered to the amount of time it takes for a wave for one complete oscillation. For example, the period of a sine and cosine function is <img src="https://latex.codecogs.com/png.image?\dpi{110}2\pi" title="https://latex.codecogs.com/png.image?\dpi{110}2\pi" />. For sales data over each month, our period will be ```12``` since there are certain events that happen anually that affects sales. Note that domain knowledge is required to choose ```m```. 
    - **t**: last known time for which we have real observation.
    - **h**: number of steps ahead that we are forecasting.
    - **k**: k finds the latest matching seasonal component (if we want to forecast for August 2022, then it finds the last known August (August 2021))
    - Note that the level ```l```and trend ```b``` both comes from time ```t``` the latest measurement.  Only the seasonal component goes further back in time to grab the appropriate point over the entire season.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/169825019-a896a03c-18bf-4ea9-adc2-40232e4e0d5a.png"/>
</p>

- the **level** equation is the same old exponential moving average. The only difference is that we subtract the previous seasonal component at index ```t-m``` from y at index ```t```.

- the **trend** equation is exactly the same as before which is the exponential moving average of the trend as measured by the difference in levels.

- The **seasonality** equation also is an exponential moving average. In front of gamma we have a ```new``` value and infront of (1 - gamma) we have the ```old``` value. Recognise that the old value comes from one period ago at index ```t-m``` and not one step ago.

#### 5.5.2 Multiplicative Model
For the multiplicative model, ```y = (level + trend) x seasonal```. If we make seasonal to be the subject of formula we get: ```seasonal = y/(level + trend)```. And this is exactly what we have in front of gamma in the seasonal equation below.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/169959629-5e0f1704-e504-407e-8e2d-165854d21fee.png"/>
</p>

Now, we will explore how the Holt-Winters model is applied on our Airline Passengers Dataset. We will define a loss function and choose the additive and the different multiplicative methods that is most appropriate.

```python
# Root Mean Squared Error
def rmse (y, yhat):
    return np.sqrt(np.mean(y - yhat)**2)
    
# Mean Absolute Error
def mae(y, yhat):
    return np.mean(np.abs(y - yhat))
```

Same as before, we create an instance of the Exponential Smoothing function and choose the additive or multiplicative method as shown below:

```python
# Additive Method
hw = ExponentialSmoothing(train['Passengers'], initialization_method='legacy-heuristic',
                         trend='add', seasonal='add', seasonal_periods=12)
```

For the additive method, we make the ```trend``` and and ```seasonal``` arguments equal to ```add```. We split our dataset for training and testing and we call the ```.fit``` method from statsmodel to choose the best smoothing parameters for the trend, level and seasonality.

```python
res_hw = hw.fit()
```

![image](https://user-images.githubusercontent.com/59663734/169967050-dd7fb319-b8df-48b8-80ca-bf0c49359c53.png)

The result is very encouraging as compared to the SES and Holt's Linear Trend model, the Holt-Winter model fits very for both train and test. Notice that the prediction is no longer lagging behind and earlier the lag was due to model mis-specification. We can also try the different multiplicative methods:

- ```y = (level + trend) x seasonal```: **Add-Mul**
- ```y = level x (trend + seasonal)```: **Mul-Add**
- ```y = level x trend x seasonal```: **Mul-Mul**

We will then use our loss function to select the model which has the least loss in the training and testng datasets. From the result below, we see that we get a better model when we ```add``` the **trend** but ```multiply``` the **seasonality** component. The RMSE is lower in the training set compared to the test set but compared to the other models, this one is doing significantly better. The same is applied when computing the MAE. 

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170880247-73f7c078-54ce-4f60-ae70-6b39edb1a858.png" width="600" height="150"/>
</p>

Using ```.params``` method, we can get the smoothing coefficients for the level, trend and seasonality:

```python
{'smoothing_level': 0.3762152620109574,
 'smoothing_trend': 3.061979771000134e-06,
 'smoothing_seasonal': 0.6237844386048091,
 'damping_trend': nan,
 'initial_level': 203.2357231696414,
 'initial_trend': 4.920913690203366,
 'initial_seasons': array([0.53805839, 0.56644619, 0.62259543, 0.59189162, 0.54698388,
        0.59792401, 0.65067508, 0.6420933 , 0.58543158, 0.51035125,
        0.45390989, 0.5234992 ]),
 'use_boxcox': False,
 'lamda': None,
 'remove_bias': False}
```


Below is the prediction for the ```Add-Mul``` model from 1957 to 1961. The green dotted lines is the forecast on the testing dataset:

![image](https://user-images.githubusercontent.com/59663734/169971211-c9abf75d-bd81-4ef5-bba6-69a3100ad84f.png)

------------------------

### 6. Time Series Analysis
In this section, we will dive deeper of the mathematical components of a time series and what transformations we need to undertake in order to fit statistical models to our data in order to do forecasting. We will follow the steps below:

1. We start with our time series which is a collection of **random variables** indexed by time.
2. We want to fit some kind of **model** to explain and understand our time series to do a **forecast**.
3. In order to do that, we need to estimate some **statistics**.
4. To do these estimations, we need our time series to be **stationary**.
5. To get a stationary time series we need to **transform** our signal to achieve weak stationarity.
6. To diagnose that we achieved weak stationarity, we will use **autocorrelation**.


#### 6.1 Deterministic dependencies: Trend and Seasonality
The most important feature of time series data is that we make no assumption about independence of these random variables. In fact, most time series data are ```dependent```, typically because **past realizations influence future observations** through the nature of the real world phenomenon that produces these data. It is fair to say, that the main goal of time-series analysis is to first ```model``` and then ```estimate from data``` (guided by the model) the **dependence structure** of these random variables.

Statistical dependence can be a boon and a curse. That is, dependence helps us make predictions about the ```future realizations``` from knowledge of the ```past realizations``` (if yesterday was warm, today will probably be warm as well). However, dependence poses technical challenges in the ```distributional analysis``` of estimators. This is because there is effectively ```less statistical information``` in ```dependent data``` about the data generating process, as compared to the case of ```independent observations``` (the basic laws of large numbers and central limit theorems do not even apply).

We can consider the following time-series examples of dependent time-series:

- Economic data: stock prices, inflation rate, GDP, employment rate, interest rate, exchange rates;

- Biometric data: heart rate, blood pressure, weight, fMRI;

- Environmental data: temperature, precipitation, pressure, humidity, pollution;

- Sound data: speech, music;

In all these examples, as well as in a general time series, data take the form of **discrete** measurements of a real world phenomena that evolves **continuously** in time. A general probabilistic model to describe such phenomena is called a **stochastic process** , which is simply a collection of random variables <img src="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" /> indexed by either a continuous or discrete time parameter ```t```. So, a time series data set can be thought of as a **single realization of a stochastic process**.

Some of the main characteristics of dependence in a time series are a trend and seasonal variation . These are deterministic dependencies of the random variables <img src="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" /> of our series on the time stamp ```t```.

Let's denote <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t)" /> as the mean function of the marginal distributions of each distinct <img src="https://latex.codecogs.com/png.image?\dpi{110}{X}_t" title="https://latex.codecogs.com/png.image?\dpi{110}{X}_t" /> in the series.  <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t)" /> contains both the ```trend``` and the ```seasonal``` variation of the series.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170673275-619db082-0370-4067-8025-7ac53bb59ff3.png"/>
</p>


 - The ```trend``` of the series, denoted <img src="https://latex.codecogs.com/png.image?\dpi{110}m_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}m_{X}(t)" />, is the ```non-constant``` and ```non-cyclical``` component of <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t)" />. Trend can be **linear** or **nonlinear**, and is often **monotone** in time. 

- The ```seasonal``` variation of the series, denoted <img src="https://latex.codecogs.com/png.image?\dpi{110}s_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}s_{X}(t)" />, is the cyclical component of <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t)" />. It is a **periodic** function whose values **repeat** at a **fixed time interval**. The period of seasonal variation may be assumed known or unknown depending on the data and application.

Thus we have the following decomposition of the deterministic dependence structure:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170673563-ac4ca4d1-0bfd-4daa-af4c-f9861bf67e60.png"/>
</p>

Normally, we model a time series as below where <img src="https://latex.codecogs.com/png.image?\dpi{110}{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}{X}(t)" /> is the value of our random variable at time ```t```. <img src="https://latex.codecogs.com/png.image?\dpi{110}\varepsilon&space;_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}\varepsilon _{t}" /> is a white noise time series, <img src="https://latex.codecogs.com/png.image?\dpi{110}m_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}m_{X}(t)" />and <img src="https://latex.codecogs.com/png.image?\dpi{110}s_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}s_{X}(t)" /> are deterministic functions of time. 

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170674167-4db96bb9-12e6-4c62-a291-443b1f881054.png"/>
</p>

Depending on the relative magnitude of the random noise and deterministic variation, the deterministic dependence in the time series may or may not be easily detectable with the naked eye.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170677285-c4856e9e-0819-4c28-9447-fcdfd653cd64.png" />
</p>

#### 6.2 Stochastic Dependence
The main stochastic feature of time series data is the statistical dependence of the random variables at different time points. Mathematically, statistical dependence of a collection of random variables means that their joint distribution is not equal to the product of their marginal distributions.


<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170680159-a7c15d71-b27e-4f24-9471-638f07aac27f.png" width="450" height="130"/>
</p>

Suppose we have two random variables ```X``` and ```Y```. Dependence means that kowledge that event ```X``` has occurred provides information about the likelihood of different values of ```Y```. 

The price of a stock tomorrow may be above or below the price of this stock today, and our expectation is that it will be equal to the price today. Because markets are ```efficient```, the best forecast of the price **tomorrow** is the price **today**. In other words, the ```change``` in the price between today and tomorrow is completely ```random``` and ```independent``` of the price today. But the **sum** of the price today with this **change** (the price tomorrow) obviously ```depends``` on the price **today**.

On the other hand, time series like **heart rate** is ```periodic``` and **temperature** has ```seasonal``` variations with a twelve months period. These time series exhibit a ```deterministic dependence```.

Very often it is the case that time series observations that are ```close``` to each other in time are ```strongly correlated```. Recall that if two variables are ```independent```, then their correlation will be ```0```. We will see more about covariance and correlation in the later chapters.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170685165-e6631e4c-7314-4cb3-83b0-e3225655bba6.png" />
</p>


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>

#### 6.3 Stationarity
We have seen how we can describe times series and what are their specificities. What we actually want to do in the end is **fit models** to time series to understand them better. In order to fit models  we need to compute statistics like ```mean```, ```variance``` and ```correlation```.

So what does it mean to compute a mean in a time series? The challenge as explained before is that we have only one random variable or one observation per time stamp. If we collect a ```100``` data points over a period of time ```t```, then we have ```100``` random variables. These are actually different random variables and we cannot just average them. What we actually have is ```one mean``` for each data point, i.e, we have **one expected value** for each day.  The same rule applies to the ```variance``` - how much my actual value deviates in expectation from the expectation from the mean. In our example, we will have ```100``` means and ```100``` variances.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170987648-d4504efb-c209-4a92-a1e7-617b35520c87.png"/>
</p>

But what we are also interested is how do the values at the different timestamps actually relate to each other? This is measured by the ```covariance```. For example, we can take data for January and June and see how they relate to each other.  

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170998937-6e7fde34-3843-4304-8458-d8b59095d8aa.png"/>
</p>

One big problem if we want to estimate this is that typically we have one time series. That is, we have only one observation for January and only one observation for June. So there's nothing we can average over. The **expected mean** would be just that **single value** of the variable that we have. And that is a problem because that's a very poor data set - only one observation to estimate means and variances or covariances.  And the only way we can typically estimate these kinds of statistics is by being able to do some kind of **averaging**.

We need a few ```assumptions``` that the summary statistics of observations are consistent that will hence, allow us to do this averaging and that are central to being able to fit models of time series. And that is the concept of ```stationarity```. Note that these assumptions can be easily violated in time series by the addition of a ```trend```, ```seasonality```, and other time-dependent structures.

> A stationary time series is one whose **statistical properties** such as ```mean```, ```variance```, ```autocorrelation```, etc. are all **constant** over time. Most statistical forecasting methods are based on the assumption that the time series can be rendered approximately ```stationary``` (i.e., "stationarized") through the use of mathematical ```transformations```. A stationarized series is relatively easy to predict: you simply predict that its statistical properties will be the ```same``` in the **future** as they have been in the **past**! The predictions for the stationarized series can then be ```"untransformed"``` by reversing whatever mathematical transformations were previously used to obtain predictions for the original series.

##### 6.1.1 Benefits of Stationarity

According to Jason Brownlee: 

- The observations in a stationary time series are **not dependent on time**.

- Time series are stationary if they do not have **trend** or **seasonal** effects. Summary statistics calculated on the time series are **consistent** over time, like the ```mean``` or the ```variance``` of the observations.

- When a time series is stationary, it can be easier to **model**. ```Statistical modeling``` methods assume or require the time series to be stationary.

##### 6.1.2 Types of Stationarity
We have to types of stationarity: ```weak``` and ```strong```.

**Weak Stationarity**

- It is a condition on the **first** and **second** statistical moments which means that all the expectations and variances throughtout the time should be the same.

- Now, we do not have one mean for each time stamp but we have only one of them. And the variance also is not different for all the different timestamps. 

- This basically enables us to estimate this **single mean** by averaging our time series because now they have the **same** mean.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171030239-61ebce8a-f3cd-4192-95fa-c419329c13be.png"/>
</p>

- For the covariance we don't say that all possible pairs of variables have the same covariance. That's a bit too strong. So we say that we have the same covariance given the **gap** between them. So the covariance is only a function of gap.

- For example, the covariance of January and July (6 months apart) has the same covariance as February and August (6 months apart). So basically every pair of months that's six months apart should have the same covariance.

- If weak stationarity holds, we can measure means and variances and covariances. We can estimate those by just averaging over the time points.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171031095-40aaad29-8662-4ec8-a8e8-874dd4e2c761.png"/>
</p>


**Strong Stationarity**

- With weak stationarity it is only the first and second moments which have to agree. However, in strong stationarity, the **entire distribution** has to be the same. 

- For example, if we take two series (5 data points each) of non-overlapping measurements, then strong stationarity states that the distribution of these two sets of measuremnts has to be exactly the same. Basically all sets of five variables, wherever we shift our window, have to be the same.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171032008-cb390206-166d-4117-b914-8f696b0e8e87.png" width="280" height="50"/>
</p>

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171043439-a0c80bb0-8d55-4fdd-862f-a470dea6e4c1.png"/>
</p>

##### 6.1.3 What breaks stationarity?

- Trend: non-constant expected value - breaks 1st condition ( <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)&space;=&space;\mu&space;_{X}" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t) = \mu _{X}" /> )
- Seasonality - breaks 1st condition ( <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)&space;=&space;\mu&space;_{X}" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t) = \mu _{X}" /> )
- Non-constant variance - breaks 2nd condition ( <img src="https://latex.codecogs.com/png.image?\dpi{110}var_{X}(t)&space;=&space;\sigma&space;^{2}_X" title="https://latex.codecogs.com/png.image?\dpi{110}var_{X}(t) = \sigma ^{2}_X" /> )
- Change in the covariance structure - breaks 3rd condition ( <img src="https://latex.codecogs.com/png.image?\dpi{110}cov(X_s,&space;X_t)&space;=&space;\gamma&space;_X(s-t)" title="https://latex.codecogs.com/png.image?\dpi{110}cov(X_s, X_t) = \gamma _X(s-t)" /> )

To sum up:

1. In order to do statistical estimation and inference with time series data, we need technical conditions about the ```stochastic process``` from which the data are drawn. The idea is to ensure that observations along a ```single realization``` of the process are ```representative``` of all possible ```realizations``` of the process that we will never get to see. Specifically, we need conditions that would allow us to **estimate** ```population parameters``` of the whole process (e.g. expectations, variances, correlations) with time averages over a ```ingle realization``` of the process. Also, we need conditions that would allow us to **extrapolate** ```statistical models``` fitted to observations from the **past** into the **future**.

2. In the statistics of ```regression analysis``` and ```maximum likelihood estimation```, we relies on random sampling (i.e., the **i.i.d.** assumption) to argue that ```sample``` averages are good estimators of the ```population``` averages in moderately large samples because of the ```LLN``` and ```CLT```. Time series data are certainly **not** ```i.i.d.``` but weak and strong stationarity enables one to do inference via time averages along a single sample path, while allowing for stochastic dependencies in the data.

3. Stationarity requires that the ```joint distribution``` of the series remains **fixed** throughout time. This means that all the ```stochastic dependencies``` in the adjacent terms of the series remain the **same** throughout time. So, if we estimate a model based on observations from ```t = 1,...,n```, then stationarity will allows us to use the ```fitted model``` to predict observations for ```t > n```.

4.  Weak stationarity does not imply strong stationarity because it says nothing about the stationarity of higher order moments of the time series.

5. However, strong stationarity implies weak stationarity because the autocovariance function depends only on the time interval between the two random variables and not on their absolute position in time. Also, strong stationarity means that the marginal distributions <img src="https://latex.codecogs.com/png.image?\dpi{110}P_t&space;=&space;P_s" title="https://latex.codecogs.com/png.image?\dpi{110}P_t = P_s" /> for all time stamps t, s. Therefore, the marginal mean <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)&space;=&space;\mu&space;_{X}(s)" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t) = \mu _{X}(s)" /> for all time stamps t, s.


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 6.4 Transformation towards Stationarity
We have seen that real-world time series data are not all stationary so we need to transform our data for it to be roughly stationary. For that, we can assume our time series to be composed of components: ```trend```, ```seasonality``` and the ```rest```.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171047239-5a103cb5-e6b4-48ba-b8a0-c8fdb9ea658e.png"/>
</p>

Since the trend and seasonality breaks stationarity then we can remove those ```2``` components and then fit the model to the rest of the time series.

##### 6.2.1 Deterministic Trend
A trend can be a linear or quadratic function of time. So we can use ```linear regression``` to model the trend. We model the estimate of the trend as shown below:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171047787-0efbb1a1-3670-4a4e-bfcc-c703db38e991.png"/>
</p>

We then transform our time series by subtracting the above T-hat:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171047895-3d80d614-bbbb-4f31-bf07-843a0e172dd2.png"/>
</p>

In the example below we have a linear trend upwards. We do a linear regression as a function of time and then we subtract that T-hat. We see that the linear upwards trend is gone in the plot on the right. There may be still some kind of curvy pattern but the linear upwards trend is gone. So that actually had to get the series closer to being stationary.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171048372-4f729361-6bf2-42bf-9136-6f7bdd1b5133.png" width="750" height="310"/>
</p>

##### 6.2.2 Deterministic Seasonality

1. To remove seasonality we fit a ```periodic``` regression model, S-hat, which we then subtract from our original time series: 

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171048754-f09e2f47-e647-4267-9e74-b3e09d85b6e4.png"/>
</p>

2. We can also subtract monthly averages. For example, if we want to use the monthly averages to remove the seasonality of summer-winter components:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171049117-d7117b62-531a-4964-92a5-6567c676fdd4.png"/>
</p>

3. We can use Fourier Analysis to decompose our series into periodic functions with different frequency.

4. Finally, we can also do ```smoothing``` - use SMA or EWMA to smooth out the summer-winter seasonality.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171049935-6beae90e-4dfd-40fc-8bf4-9526610f5ad2.png" width="500" height="250"/>
</p>

##### 6.2.3 Non-linear Transformation

Bside ```trend``` and ```seasonality```, variation that changes over time also breaks stationarity. Changing the values of the series with a ```log
transformation``` can actually help a lot.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171049876-dd8abf8c-86c6-4cf1-b7d3-3071e9a568b7.png" width="700" height="270"/>
</p>


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


##### 6.2.4 Differencing
There's another technique that exists where we do not actually have to do the explicit ```decomposition```. This is called **differencing** or **differentiation**. When differencing we create a new time series which is the difference between consecutive values. 

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171114204-0cbb05cf-19b5-4802-85e6-202c3e33503c.png"/>
</p>

Let's prove how differencing can help remove stationarity. Suppose we have this simple non-stationary time series <img src="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" /> which is a linear model for some <img src="https://latex.codecogs.com/png.image?\dpi{110}\beta&space;" title="https://latex.codecogs.com/png.image?\dpi{110}\beta " /> plus some i.i.d. Gaussian noise.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171115387-838b8e2e-dfab-40bc-ae63-eb093a0669db.png"/>
</p>

When we do differencing, we have our new time series <img src="https://latex.codecogs.com/png.image?\dpi{110}Y_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}Y_{t}" /> which constitute of one of the betas plus a difference of these white noises which are indendent of time. <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu(X)&space;=&space;\beta&space;&space;" title="https://latex.codecogs.com/png.image?\dpi{110}\mu(X) = \beta " /> and the variation is determined by the difference of these random variables.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171116616-0651365a-3109-4ebf-889c-cb8ceced0849.png"/>
</p>

The covariance also doesn't change over time anymore because it's just determined by these random variables. So differencing **one** time removes ```linear trend``` and differencing a **second** time removes ```quadratic trend```.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171118023-5878e506-d7d2-4403-8387-e5f8aeba2913.png"/>
</p>

In general, if we need to differentiate ```p```times for <img src="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" /> to become stationary, then we say that the series <img src="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" /> is integrated of order ```p```.

Below is an example of a time serues when we remove linear trends and when we do differencing. While they kind of have a similar effect, the actual outcome doesn't look exactly the same. In both of the transformations, the linear trend is removed. But the differencing also remove the other curvy patterns that we still have in the detrended time series.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171118771-c8f15ec6-e9a1-4e92-9359-6c4bbccd7f21.png" width="400" height="500"/>
</p>

Now which transformation - removing trend, removing seasonality or differencing -  should we choose to make our time series stationary?

- When we decompose our time series, we know exactly what is our trend or seasonality so this makes us understand the time series better. However, on the other hand, we need to choose what kind of seasonality of trend we would need to subtract it from the original time series.

- Differencing is quite simple and straight-forward. We do not need to choose any models and we can also use differencing together with logarithm. However, when doing differencing it shortens our time series so this make not be appropriate for short time series. Differentiation of the time series not only removes the trend (i.e. ```deterministic dependence``` on time) but also removes ```stochastic dependence``` on the past terms of the series.

In summary:

1. Fitting a ```linear regression model``` of the series on the time index and subtracting off the fitted mean function from the series removes the ```linear trend```. 

2. A **nonparametric regression model** can be used to estimate and remove a ```nonlinear``` (and hence also a ```linear```) trend from a time series. A nonparametric regression can be used to estimate and remove ```seasonal``` variation (which can be seen as a ```nonlinear trend```), but it is much more statistically efficient to use a **parametric** regression on a ```periodic``` function to do this.

3. Fitting a ```periodic regression``` function to a time series can be used to estimate and remove ```seasonal``` variation.

4. Differencing the data **once** can be used to remove a ```linear trend``` and differencing the data **more than once** can be used to remove ```polynomial trends```. Differencing the data is also a standard method to transform a time series with ```exploding variance``` and persistent stochastic dependence into a stationary time series. If the increments of a time series rather then its levels are stationary, then the first difference of the series is stationary. 

5. A **variance reducing transformation** like the ```log``` can stabilize the increasing variance of a time series. However, this does not help with persistent dependencies in the time series.


<p align="center">
________________________________________________________ .. __________________________________________________________
</p>


#### 6.6 Diagnosing Stationarity
We saw how we can decompose our time series or use differencing to make our time series stationary. Now, we could only observe visually if our time series seem to be visually or not. We did not have any mathematical model that can guarantee us that the signal is indeed weak stationary. In this section, we will explore the ```autocorrelation function``` or the ```correlogram``` which will provide us a way to diagnose when our data is stationary.

##### 6.4.1 Sample Estimates for Stationary Series
Let <img src="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" title="https://latex.codecogs.com/png.image?\dpi{110}X_{t}" /> denote a stationary time series. Recall that this implies that the marginal mean function <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}(t)" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}(t)" /> is constant and the autocovariance function depends only on the difference of the two time stamps. We obtain **estimators** of the mean <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu&space;_{X}" title="https://latex.codecogs.com/png.image?\dpi{110}\mu _{X}" /> , the variance <img src="https://latex.codecogs.com/png.image?\dpi{110}\sigma&space;^2_{X}" title="https://latex.codecogs.com/png.image?\dpi{110}\sigma ^2_{X}" /> and the autocovariance function <img src="https://latex.codecogs.com/png.image?\dpi{110}\gamma&space;_{X}(h)" title="https://latex.codecogs.com/png.image?\dpi{110}\gamma _{X}(h)" /> by replacing expectations with ```sample averages```:

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171175670-43692277-b328-46a4-9ddf-0a0298f65d69.png" width="400" height="200"/>
</p>

If the series is stationary, then each observation in the sample averages above contributes statistical information about the common parameters <img src="https://latex.codecogs.com/png.image?\dpi{110}\mu,&space;\sigma&space;^2,&space;\gamma&space;(h)&space;" title="https://latex.codecogs.com/png.image?\dpi{110}\mu, \sigma ^2, \gamma (h) " />. However, most time series are ```dependent```. However, if the ```stochastic dependences``` (e.g. **correlations**) in the series decays sufficiently fast as the time distance between terms get large, then the sample averages have a similar asymptotic behavior as in the classical ```laws of large numbers``` and ```central limit theorems``` for i.i.d. data. So, under mild technical conditions, we have good **estimators** of the mean, variance and autocovariance function of a stationary time series.

##### 6.4.2 Autocovariance Function (ACF)
The autocovariance function (ACF) is a very useful statistical tool for studying the dependence properties of a time series. The ACF is our formal tool for detecting non-stationarity in a time series. Plotting and visualizing the correlation structure of the series is the second step after plotting and visualizing the series itself. 

The "auto" part in autocovariance tells us that two random variables come from the same time-series. Covariance is just the ```unscaled correlation```. Therefore it tells us how related two random variables are. If they are completely **unrelated**, then the correlation and hence the covariance will be ```zero```. If they are **related**, that is, they move together either in the same direction or the opposite direction, then this value will be ```non-zero```.

Recall in weak stationarity the autocovariance is just a function of the ```gap```, i.e, if we pick any two time points in the series, as long as this time difference is the same, the covariance between these two random variables is the same. In other words, the relationship between each value and the time series remains constant over time. If this relationship were to change over time, then we wouldn't be able to fit any such model. That's why we want stationary when we fit these kinds of models.

Note that this also implies that the variance remains constant over time. So that's why if we see the variance change over time, as we do with ```volatility clustering```, then we take that as evidence that thetime series is non-stationary. 

A ```correlogram``` is a chart which shows correlation in data that changes over time. The x-axis is the **lag**, **h**, and the y-axis is the **autocorrelation** with range of ```-1``` to ```+1```. Below is a series of time series with their correlogram at different values of lag. If we see any lagged autocorrelations outside the confidence threshold, we will **reject** that they are equal to ```0```. 

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171180679-114db3df-77ee-4a05-a547-ed723b074cc1.png"/>
</p>

We can use the ACF as a diagnostic tool after transformations to check whether the series is stationary or if there is any kind of patterns left. The autocorrelation tells us about how the linear dependence between the values at different time lags. Note at lag ```0``` the autocorrelation is ```1``` because we are simply dividing the variance by the variance.

<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/171183313-b83b8144-cf2b-45da-89e9-205e14311157.png" width="800" height="400"/>
</p>



<p align="center">
________________________________________________________ .. __________________________________________________________
</p>









------------------------------


#### 6.4 Autoregressive Models - AR(p)

Earlier we worked on SMA and EWMA as a way to compute the average of our time series. We used SES that modeled the EWMA to do forecasting. Holt's Linear Trend and Holt-Winters were used for forecasting on seasonal datasets which may also have a trend. To make it more distinct, Exponential Smoothing is used for a specific kind of data which model linear trend and seasonality. 

Unfortunately we could not really use it in our stock prices datasets because we do not have seasonality in such data. Recall that stock prices follow a ```random walk``` and hence, we need a more robust model for prediction - the **ARIMA model**.

Contrary to Exponential Smoothing model, Arima models are more in the spirit of modern machine learning, where we take a model and you try to fit it to our data, whatever structure our data may have. Auto regressive models are basically ```linear regression``` models where the inputs also known as the ```predictors``` are past data points in the time series.



<p align="center">
  <img src= "https://user-images.githubusercontent.com/59663734/170880177-8c01ea3a-3f3c-40d6-87cb-3be5a3790012.png" width="620" height="230"/>
</p>











<p align="center">
________________________________________________________ .. __________________________________________________________
</p>










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
18. https://www.investopedia.com/terms/s/seasonality.asp#:~:text=Seasonality%20is%20a%20characteristic%20of,is%20said%20to%20be%20seasonal.
