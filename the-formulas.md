---
description: This page shows the formulas used in mimo protocol.
---

# 公式

## 自动做市

在每笔交易中，用户可以用一定数量的特定代币对一定数量的另一种代币进行交易兑换，价格由公式进行定义。MIMO没有使用传统的交易委托账本和待执行机制。

mimo 使用的公式是基于自动做市\(AMM\)的 DEX 广泛采用的著名公式$$x * y = k$$，例如 uniswap。

## 公式  $$x * y = k$$ 

假设$$X$$这是源代币， $$Y$$是目标代币。在 mimo 中，$$X$$, $$Y$$可以是 IOTX 或任何 XRC20 令牌。 设$$x$$,$$y$$分别为当前流动性池中的 X-token、Y-token。

基于著名的 AMM 方程

$$
x * y = k
$$

公式中的$$k$$ 是一个常数。

 $$x$$和 $$y$$的乘积在交易前后保持不变。详情请参考[vbuterin的帖子](https://ethresear.ch/t/improving-front-running-resistance-of-x-y-k-market-makers/1281)。

## 基于输入值的定价

Let's further define $$d_x$$ , $$d_y$$ are how many X-tokens you want to pay, and  how many Y-tokens you will get, respectively.

We'd like to know, the price based on $$d_x$$ or$$d_y$$.   If`getInputPrice` denotes how many Y-Tokens \(i.e. $$d_y$$ \) can be bought by selling a given $$d_x$$, 

让我们进一步定义 $$d_x$$ , $$d_y$$，分别是您想要支付的X-token的数量，以及您将获得的Y-token的数量。

我们需要知道，价格是基于$$d_x$$或$$d_y$$的。如果用`getInputPrice`表示通过出售给定的$$d_x$$可以购买的Y-token的数量（即$$d_y$$ ），则：

$$
getInputPrice(x, y, d_x) = \dfrac{y * 997 * dx}{1000 * x + 997 * d_x}
$$

在代码中表示为：

```javascript
getInputPrice(x, y, dx) = (y * 997 * dx) / (1000 x + 997 dx)
```

如果`getOutputPrice` 表示购买$$d_y$$ Y-tokens需要的X-token的数量 ,则：

$$
getOutputPrice(x, y, d_y) = \dfrac{1000 * x * d_y}{(y-d_y)*997} + 1
$$

在代码中表示为：

```javascript
getOutputPrice(x, y, dy) = 1000 x * dy / ((y - dy) * 997) + 1
```

where `/` in above equations denotes `divToInteger`, which means divide with rounding to floor of the results.

上方等式中的 `/` 表示 `divToInteger`，意为除以四舍五入到结果。

## 价格影响因素

在AMM中，兑换汇率会在每次交易后发生变化，也会在 $$d_x$$ , $$d_y$$ 和  $$x, y$$池中的流动性发生变化后变化。因此，价格影响因素是交易者们在交易前希望知道的。



有两种支持计算价格影响的方法。它可以基于 $$x, y, d_x$$或$$x, y ,d_y$$。一种是基于输入值，一种是基于输出值。

$$
PriceImpact(x, y, d_x) = \frac{ (1000*x)^2} { (1000*x + 997*d_x)^2} -1
$$

或

$$
PriceImpact(x, y, d_y) = \dfrac{(y-d_y)^2}{y^2} -1
$$

在代码中表示为：

```javascript
price impact(x, y, dx) = (1000*x)^2 / (1000*x + 997*dx)^2 - 1
price impact(x, y, dy) = (y - dy)^2 / y^2 - 1
```

请注意，价格影响始终介于 `-1` 和 `0` 之间。

## 交叉交易价格影响因素

如果两个代币之间没有直接交易对，比如在 V1 中我们只支持 IOTX/XRC20交易对，交易者需要使用一个代币，例如 IOTX，作为两个代币之间交易的桥梁。

在这种情况下，价格影响公式将是

$$
PriceImpact_{cross}  = PI_1 * PI_2 + PI_1 + PI_2
$$

在代码中表示为：

```javascript
price impact = PI1 * PI2 + PI1 + PI2
```

当中，

```text
PI1 is the price impact of first trading pair, such as x to IOTX
PI2 is the price impact of second trading pair, such as IOTX to y
```



