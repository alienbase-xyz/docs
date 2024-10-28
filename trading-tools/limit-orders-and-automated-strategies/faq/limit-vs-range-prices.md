# Limit vs Range Prices

Automated Strategies offer two distinct trading options, allowing users to trade tokens at either a constant rate or a variable rate. Understanding these options will enable you to make informed trading decisions.

#### Price Limit <a href="#price-limit" id="price-limit"></a>

**Definition**

A trading strategy where users offer to trade tokens at a fixed rate.

**How it Works**

* Users set a specific price at which they wish to trade their tokens.
* This operates similarly to a traditional limit order.
* The offered tokens are available for other market participants to exchange at the specified rate.

**Example**

A user offers to buy ETH at a constant price of 2,000 USDC per ETH. They provide a certain amount of USDC, which will be exchanged at this rate by other traders.

When setting a strategy with a specific price limit, the public indication is similar to limit orders where you indicate that the number of tokens allocated for this action (buy/sell) are available for anyone (traders or market makers) to take at that specific price. It also means that ALL the allocated liquidity will be available at that exact price making it very concentrated at that price point and allowing trade with no slippage against it.

#### Price Range <a href="#price-range" id="price-range"></a>

The Price Range option is advanced and requires a good understanding of its mechanics.

**Definition**

A trading strategy where users offer to trade tokens at a variable rate, determined by the remaining quantity of tokens they have.

**How it Works**

* Users set a price range within which they are willing to trade.
* The starting and ending prices of this range are equivalent to the initial and terminal marginal exchange rates.
* As market participants interact with this order, the observed exchange rate adjusts. The observed exchange rate is always equal to the geometric mean of the marginal exchange rates before, and after the swap is performed.

**Example**

A user offers to buy ETH at a price range starting at 2,000 USDC per ETH and ending at 1,000 USDC per ETH. As other market participants exchange their ETH for USDC, the marginal bidding price recedes from 2,000 USDC per ETH down to 1,000 USDC per ETH, until the position's USDC reserves are depleted.

When setting a strategy with a price range, the allocated budget will be spread across ALL available price points in the bonding curve that is created between the two price points. Few things to note when using this option:

1. The "average price" for a range is actually the geometric mean, not to be confused with the arithmetic average:

```
Example: 
  Arithmetic mean between 1800-2000 = 1900
   Geometric mean between 1800-2000 = 1897.37
```

2. The amount of price points between 1 DAI value change is 10^18 as there will be a price point for every wei change in price.

```
Example:
Between 1800-1801 
1800.000000000000000000
1800.000000000000000001
1800.000000000000000002
1800.000000000000000003
...
1800.999999999999999997
1800.999999999999999998
1800.999999999999999999
1801.000000000000000000
```

3. The budget per price point is sliced very thin.

```
Example:
Splitting 100 ETH across 1 DAI price change will split 
100/10^18 = ~0.0000000000000001 ETH per price point 
(this is estimation as due to the curve effect, the distribution is not equal across all price points)
```

{% hint style="info" %}
It is recommended to use the price limit option until you are familiar with the math and calculations of the price range option.
{% endhint %}
