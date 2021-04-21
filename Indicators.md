
# Indicators

Technical analysis focuses on historical prices and trading volumn rather than evaluating companies. The historical data allows technical analysts to compute statistics called "indicators". **Indicators** are heuristics that hint at a buy or sell opportunity.

There are four main types of indicators: trend, momentum, volumn, and volatility.

Some common idicators are:
1. Momentum
2. Simple moving average (SMA)
3.  Bollinger Bands

Individual indicators are generally weak predictors of price. Combinations of indicators are more successful. They are also more valuable over shorter time horizons. They are also useful for identifying contrasts between different stocks.

## Normalization of Indicators

```
normalized_result = (values - mean) / values.std()
```

## Momentum

The momentum is a calculation of how much the price has changed over some time interval (days, weeks, etc.).

```
momentum[t] = price[t] / (price[t-n] - 1)	
```

## Simple Moving Average

The simple moving average (SMA) is an average over an n-day window. 

There are two general ways traders use the SMA. First, they look for places where a stock has strong momentum and its price passes through the SMA. Second, traders use SMA as a proxy for a stock's true value and look for cases when the stock's price significantly diverges from the SMA.

```
SMA[t] = price[t] / price[t-n:t].mean() - 1
```

## Bollinger Bands

The Bollinger Bands® (BB) are used to determine *when* the divergence of the share price from the simple moving average (SMA) indicates a buy or sell signal. As an indicator, BB combine a measure of volatility and a simple moving average (SMA) over *N* days. Volatility is determined by the standard deviation of prices over *N* days. The upper BB is set two standard deviations above the SMA and the lower BB is set two standard deviations below the SMA.

```
simple_moving_avg = mean(prices for N days)
upper_band = simple_moving_avg + std_dev(prices for N days) * 2
lower_band = simple_moving_avg - std_dev(prices for N days) * 2
```

When reading BB, look for the following:
1. As volatility increases, the upper and lower bands widen. As voltility decreases, the bands narrow and move closer to teh SMA.
2. A _buy_ signal occurs when the price crosses from outside to inside the lower band.
3. A _sell_ signal occurs when the price crosses from outside to inside the top band.

Note that a _buy_ signal does **not** occur when the share price drops below the lower band because the price might be in a larger downard trend. Note that a _sell_ signla does **not** occur when the share price breaks out of the upper band because the price might be in a larger upward trend. In both cases, the assumption is that the buy/sell signal occurs once the share price starts trending back toward the SMA.

![[bollinger_bands_hrl.png]]

## Relative Strength Index

The **Relative Strength Index** (RSI) is a momentum indicator used to determine the velocity of share price movements to detect price trends. The RSI is calculated using the **Relative Strength** (RS) and then normalizing the RS. 

To calculate the RS, average the gains and losses for a stock over *N* periods and then divide the average gain by the average loss. 

$$RS = \frac{AvgGains_n}{AvgLosses_n}$$ 

The RSI calculation is then:

$$RSI = 100 - \frac{100}{1 + RS}$$

This calculation generates a score between 0 and 100. A score below 30 indicates the asset is *oversold* in the market. A score above 70 indicates the asset is *overbought* in the market.

![[relative_strength_indicator.png]]

## Exponential Moving Average

**Exponential Moving Average** (EMA) is a lagging, trend indicator. It differs from a simple moving average (SMA) because it weights recent price movements higher than later price movements. 

The EMA is calculated over *N* periods:

$$EMA = (close - EMA_{yesterday}) * weightMult + EMA_{yesterday}$$

1. Subtract the previous day’s EMA (the SMA is used for the first value) from today’s close price. 
2. Multiply the result by a weight multiplier:  $weightMult = \frac{2}{periods_n + 1}$
3. Add the previous day’s EMA to the result of (2).

A typical trading strategy might use a long and short EMA to detect buy and sell signals.

![[exponential_moving_average.png]]

## Moving Average Convergence Divergence

**Moving Average Convergence Divergence** (MACD) is a momentum indicator that tracks the convergence and divergence of two EMA indicators. 

To calculate the MACD subtract a long EMA from a short EMA. The divergence between the two EMA indicates strong momentum in the price trend (up or down). Increasing negative MACD values indicate downward momentum and increasing positive MACD values indicate upward momentum.

$$MACD = EMA_{short} - EMA_{long}$$

The MACD line is plotted with a signal line that’s an EMA of the MACD and a “histogram” that’s the difference of the MACD and signal line.

$$MACD_{hist} = MACD - SignalLine$$

![[moving_avg_conv_div.png]]

## Ulcer Index

The **Ulcer Index** (UI) is a risk, or volatility, indicator that's an alternative to standard deviation. It measures volatility as the expected price decrease of a share over *N* periods. 

Calculate UI by taking the square root of the squared average of the percent drawdown over *N* periods.

$$UlcerIndex = \sqrt{\frac{(\sum_n{PercentDrawdown})^2}{n}}$$

The drawdown percent is calculated as today’s close price minus the max close over *N* periods divided by the max close over *N* periods.

$$PercentDrawdown = \frac{(TodayClose - MaxClose_n)}{MaxClose_n * 100}$$

High UI scores indicate high risk of drawdown whereas low UI scores indicate low risk.

![[ulcer_index.png]]