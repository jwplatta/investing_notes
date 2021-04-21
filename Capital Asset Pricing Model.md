# Capital Asset Pricing Model

## Definition of a Portfolio

A **Portfolio** is a weighted set of assets. 

$w_i$ is the portion of funds in asset $i$. The sum of the absolute values of the weights of each stock in the portfolio must equal 1.0:
$$\sum_i{abs(w_i)} = 1.0$$

And so portfolio returns is determined by:
$$r_p(t) = \sum_i{w_i r_i(t)}$$

(Where $w_i$ is the weight of asset $i$ in the portfolio and $r_i(t)$ is the return of asset $i$ on date $t$.)

## CAP Weighted

Market behavior is typically tracked with indexes. Most of the major indexes are **Cap weighted** which means each stock in the portfolio/index is weighted by that stock's market capitalization. 

To get the weight $w_i$ of a particular company, divide that company's market capitalization by the sum of all the index's companies' market capitalizations: 
$$w_i = \frac{mktCap_i}{\sum{mktCap_n}}$$

## Beta and Alpha

The return $r$ for an individual stock at a date $t$ is equal to $\beta_i$ times the return on the market $r$ at that date plus $\alpha_i$ of that particular stock on that date:
$$r_i(t) = \beta_ir_m(t) + \alpha_i(t)$$

The CAPM equation asserts that significant portion of the return on a stock is due to the market. $\beta$ encapsulates the degree to which the stock is affected by the market. 

The _residual_, $\alpha$, the difference between how the stock actually performs what $\beta$ predicts. The expectation, i.e expected value, for $\alpha$ is zero.

$\beta$ and $\alpha$ are calculated from daily returns. For example, compare the S&P500 against XYZ. Suppose the daily return for the S&P500 and XYZ are plotted against each other like below. $\beta$ is the slope of the red line and $\alpha$ is the y-intercept of the red line. In this case, the y-intercept is outside the graph at 0.438.

![[beta_alpha.png]]


## CAPM for Portfolios

To calculate the CAPM return $r_{portfolio}$ for an entire portfolio at a date $t$, sum the CAPM for each stock multiplied by its weight $w_{stock}$:
$$r_{portfolio}(t) = \sum_{stock} {w_{stock} (\beta_{stock}r_m(t) + \alpha_{stock}(t))}$$

To calculate $\beta$ for the entire portfolio simply take the weighted sum of the individual betas for each of the stocks:
$$\beta_{portfolio} = \sum_{stock}{w_{stock} \beta_{stock}}$$

## CAPM vs Active Management

**Passive** buy index funds and hold.

**Active** pick stocks.

CAPM makes two claims about $\alpha$. First, $\alpha$ is random and cannot be predicted. Second, its expected value is 0.

So, the CAPM formula for passive portfolios:

$$r_{portfolio}(t) = \beta_{portfolio}r_m(t) + \alpha_{portfolio}(t)$$

Or:

$$r_{portfolio}(t) = \beta_{portfolio}r_m(t) + 0$$

On the other hand, active managers claim that they can predict $\alpha$. The CAPM formula for actively manageed portfolios:

$$r_{portfolio}(t) = \beta_{portfolio}r_m(t) + \sum_{stock}{w_{stock}\alpha_{stock}(t)}$$

## Implications of CAPM

Since, according to CAPM, $\alpha$ is random and its expected value is zero, it's not an available tool for making money. So, the only way to beat the market is to cleverly choose $\beta$. When the market moves upwards, we try to choose a positive $\beta$ and when the market moves downwards, we try to choose a low $\beta$. Thus, CAPM claims that you cannot beat the market.

One problem with CAPM is the [[Efficient Markets Hypothesis]] which claims you can't predict the market. This hypothesis implies that not even $\beta$ is available as a tool for maximizing portfolio value.

## How Hedge Funds use CAPM

A hedge fund seeks actionable information that can be converted into a forecasted $/alpha$ and estimated $/beta$ for stocks in its portfolio. The hedge fund uses CAPM to minimize risk by finding $/beta_{portfolio}$ equal to zero. This $/beta_{portfolio}$ is determined by finding the appropriate weights for the stocks in the portfolio. This minimizes the exposure of the portfolio to the market and allows the fund to focus on $/alpha$. The **hedged** position, i.e. going long and short, is one way to achieve the desired portfolio.
