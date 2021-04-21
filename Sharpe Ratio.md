
# Sharpe Ratio

The **Sharpe ratio** adjusts return for risk. The ratio provides a way to assess different stocks given their volatility and return.

[Insert picture of stocks with differen volatilities and returns]

All else being equal, the ratio assumes:
1. Lower risk is better
2. Higher return is better

The _ex antea_ formulation of the Sharpe ratio:

$$sharpeRatio = \frac{mean(dailyReturns - dailyRiskFreeRate)}{std(dailyReturns - dailyRiskFreeRate)}$$

The ratio also incorporates the **risk free rate of return**, or the return on a risk free assest such as a savings account. As of 2015, the risk free rate is ~0%. Some sources for the risk free rate are:
- LIBOR
- 3-month treasury bill
- 0%

Usually the risk free rate is given on an annual basis. The _daily_ risk free rate is calculated the following way:

$$dailyRiskFreeRate = \sqrt[252]{endOfYearValue} - 1$$

The Sharpe ratio can vary based on how frequently it's sampled. The Sharpe ratio was originally intended to be an annual measure. So, it sampling at daily or monthly frequency, then an adjustment factor, $K$, is added where $K = \sqrt{samplesPerYear}$. For example, if the sample frequency is daily, there are 252 trading days in the year, so $K = \sqrt{252}$ and the $annualizedSharpeRatio = K * SharpeRatio$. So, the daily Sharpe ratio:
$$dailySharpeRatio = \sqrt{samplesPerYear} * \frac{mean(dailyReturns - dailyRiskFreeRate)}{std(dailyReturns)}$$