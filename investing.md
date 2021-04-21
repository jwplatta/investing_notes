# Investing

## Details

- 252 trading days
- Use SPY as a reference for other stocks

## Stock Statistics
- Daily returns
- Average daily return
- Portfolio return
- Cumulative returns
- Calculate Portfolio Value:
1. Normalize prices
2. Allocations
3. Position Values
4. Sum Portfolio Values

- Risk: standard deviation or volatilty 

## Correlation of Stock Prices

- Scatterplot correlating two stocks
- Beta
- Alpha
- Slope is not correlation
- Linear regression

## Sharpe Ratio
[[Sharpe Ratio]]


## Portfolio Optimization

- Example code here

## Types of Funds

- ETF
	- Buy/sell like stocks
	- baskets of stocks
	- transparent
	- Managers of ETFs are compensated by an _expense ratio_ which is some percent of the AUM. They are usually pretty low, e.g. 0.01% or 1.00%.
- Mutual Funds
	- Only buy/sell at end of the day
	- Quarterly disclosure
	- Less transparent
	- Managers of mutual functions are compensated by an _expense ratio_ that are typically higher than ETFs.
- Hedge Funds
	- Buy/sell agreement
	- No disclosure
	- Not transparent
	- Hedge fund managers are compensated with an expense ratio of 2% and 20% of the profits.

**Liquidity** is the ease with which one can buy/sell shares in a particular holding.

**Capitalization** is the value of a company according to the number of shares outstanding times the share price.

**Assets Under Management** (AUM) is the amount of money managed by a given fund.

## Types of Investors

- Individuals, e.g. high net worth individuals
- Institutions, e.g. retirement funds or educational institutions
- Funds of funds

- Hedge goals
	- Beat a benchmark
		- e.g. beat the SP500
	- Absolute return
		- Long/short
	- Metrics used to track progress towards these goals:
		- Cumulative return
		- Volatility
		- Risk/reward (measured using the Sharpe ratio)


## Market Mechanics

Market components:
- Individuals
- Brokers
- Exchanges
- Dark Pools
	- Brokers use dark pools to save money by avoiding exchange fees.

Components of an order:
- Buy or sell
- Symbol
- Shares
- Limit or market order
- Price (only for limit orders)

**Limit** order: will not do any worse than a specified price.

**Market** order: willing accept the market price.

**Order-book** Each exchange keeps an order book for every stock that's bought or sold there.

**Geographic Arbitrage**

Other types of orders:
- **Stop loss** sell when the stock reaches a certain _low_ price.
- **Stop gain** sell when the stock reaches a certain _high_ price.
- **Trailing gain** combines stop loss and stop gain
- **Selling short** take a negative position on a stock.
	- Borrow N shares from A
	- Immediately sell those shares to B
	- Then, at a later time, buy N shares from C at a lower price
	- Return the N shares to A


## Value of a Company

**Monotonically** always increasing.

Ways of determining a company's value:
1. **Intrinsic value** estimating company's value based on future dividends
2. **Book value** assets the company owns. 
	1. Total assets minus intangible assets and liabilities.
3. **Market cap** shares * share price

Present value of a dollar delivered in the future. Present value is worth some fraction of future value.

$$PV = \frac{FV}{(1 + IR)^i}$$

where $i$ is how far into the future this payment will be delivered and $IR$, the interest rate, is determined by the U.S. government.

**Discount Rate** The discount rate is higher if the company is less certain to pay the divident. The discount rate is lower if the company is _more_ certain to pay the dividend.

How do account for the discoun rate? What is the the future value of all the dividends that a company is going to pay me? 

Intrinsic value:

$$\sum_{n=1}^{\infty} \frac{FV}{(1 + IR)^i} = \frac{FutureValue}{(n - 1)} = \frac{FutureValue}{DiscountRate}$$

where $n = (1 + IR)^i$

For example suppose that a company pays a dividend of $2.00 per year with a discount rate of 4%. Then, the intrinsic value of the company is 2.00 / 0.04 = $50.

[[Capital Asset Pricing Model]]

[[Arbitrage Pricing Theory]]

[[Indicators]] vs [[Fundamental Analysis]]

[[Market Mechanics]]

[[Short Selling]]

[[Trading Strategies]]