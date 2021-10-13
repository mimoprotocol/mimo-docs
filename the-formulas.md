---
description: This page shows the formulas used in mimo protocol.
---

# The Formulas

## Automated Market Making

In each trade, traders trade certain amount of a particular token for certain amount of another token with the price defined by a formula. There is no orderbook and waiting for fulfillment. 

The formula that mimo uses is the famous  $$x * y = k$$ that has been widely adopted by AMM based DEX, such as uniswap. 

## The formula $$x * y = k$$ 

Assume that$$X$$ is the source token, and $$Y$$ is the destination token. In mimo, $$X$$, $$Y$$ could be either IOTX or XRC20 tokens. Let $$x$$, $$y$$ be X-token, Y-token in current liquidity pool, respectively.

Based on the famous AMM equation 

$$
x * y = k
$$

where $$k$$ is a constant. 

The product of $$x$$ and $$y$$ remains the same before and after trading. For details, please refer to [vbuterin's post](https://ethresear.ch/t/improving-front-running-resistance-of-x-y-k-market-makers/1281). 

## Pricing based on the inputs

Let's further define $$d_x$$ , $$d_y$$ are how many X-tokens you want to pay, and  how many Y-tokens you will get, respectively.

We'd like to know, the price based on $$d_x$$ or$$d_y$$.   If`getInputPrice` denotes how many Y-Tokens (i.e. $$d_y$$ ) can be bought by selling a given $$d_x$$, 

$$
getInputPrice(x, y, d_x) = \dfrac{y * 997 * dx}{1000 * x + 997 * d_x}
$$

or in  code,

```javascript
getInputPrice(x, y, dx) = (y * 997 * dx) / (1000 x + 997 dx)
```

If  `getOutputPrice` denotes how many X-tokens is needed to buy $$d_y$$ Y-tokens,

$$
getOutputPrice(x, y, d_y) = \dfrac{1000 * x * d_y}{(y-d_y)*997} + 1
$$

or in code,

```javascript
getOutputPrice(x, y, dy) = 1000 x * dy / ((y - dy) * 997) + 1
```

where `/` in above equations denotes `divToInteger`, which means divide with rounding to floor of the results.

## Price impact

In AMM, the price would change after each trade, $$d_x$$ , $$d_y$$ and  $$x, y$$ the liquidity in the pool. The price impact is what traders want to know before the trade. 

There are two ways of calculating price impact. It can be based on $$x, y, d_x$$ , or $$x, y ,d_y$$ . One is based on input , one is based on output. 

$$
PriceImpact(x, y, d_x) = \frac{ (1000*x)^2} { (1000*x + 997*d_x)^2} -1
$$

or

$$
PriceImpact(x, y, d_y) = \dfrac{(y-d_y)^2}{y^2} -1
$$

in code,

```javascript
price impact(x, y, dx) = (1000*x)^2 / (1000*x + 997*dx)^2 - 1
price impact(x, y, dy) = (y - dy)^2 / y^2 - 1
```

Note that the price impact is  always between `-1` and `0`.

## Cross-Trading Price Impact

If there are no direct trading pairs between two tokens, like in V1 where we only support IOTX/token pairs, traders need to use one token, such as IOTX, as a bridge to trade among two tokens. 

In this case, the price impact would be

$$
PriceImpact_{cross}  = PI_1 * PI_2 + PI_1 + PI_2
$$

or in code,

```javascript
price impact = PI1 * PI2 + PI1 + PI2
```

where

```
PI1 is the price impact of first trading pair, such as x to IOTX
PI2 is the price impact of second trading pair, such as IOTX to y
```

