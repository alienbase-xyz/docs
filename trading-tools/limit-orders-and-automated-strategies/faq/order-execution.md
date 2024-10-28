# Order Execution

Automated strategies are created by individual users known as “makers” and composed of one or two on-chain limit and range orders. Execution of a maker's orders require the involvement of “takers” -- i.e., spot traders such as direct traders on "Swap", arbitrageurs and DEX aggregators.

The settings of each user's strategy, the strategy's liquidity, total network liquidity in the token pair, as well as network congestion affect the likelihood of execution in their strategy.

### Liquidity and Ranges <a href="#liquidity-and-ranges" id="liquidity-and-ranges"></a>

Makers submit orders with their custom ranges defining the prices at which they’re willing to buy or sell their tokens. An order with a relatively wide range spreads liquidity across a larger number of prices, whereas an order with a relatively tight range concentrates liquidity within a smaller number of prices. Orders with more liquidity concentrated at a given price are more likely to get their orders executed when the market moves into that price.

For example, consider two separate orders to buy ETH using USDC. Both orders are funded with the same amount of USDC tokens, but have different sized ranges.&#x20;

Jen's `Order A` offers to buy ETH in the range of 1800-1900 USDC.&#x20;

Tom's `Order B` offers to buy ETH in the range of 1800-2000 USDC.&#x20;

Jen's order slices the allocated budget across a tighter range, which means more tokens per each price point in the range. When the external market price of ETH reaches 1800, Jen's `Order A` is more likely to execute first, since it has a larger amount of liquidity concentrated at 1800 and can therefore offer a better price to the taker.

### Gas <a href="#gas" id="gas"></a>

Gas cost is also factored into spot trading requests. A maker order may be offering a price that is desirable for takers, however the gas costs involved with filling the trade may make the trade undesirable, resulting in non-execution. The same holds true for arbitrageurs. Typically an arb takes trades (and executes the relevant maker order) if it is profitable for the arb to do so, and such profit measurements include the current cost of gas.

## 100% Fill Estimation

When creating a new strategy or editing an existing one, a value called "100% filled estimation" is exposed for ease of use.

#### Goal of estimation <a href="#goal-of-estimation" id="goal-of-estimation"></a>

The 100% filled estimation is an indication to makers on the amount of tokens the strategy will hold, should the entire budget be used. Once the order(s) details are provided, the buy or sell average price is identified and multiplied by the entire budget.

#### Calculation <a href="#calculation" id="calculation"></a>

**Price aspect**

1. Limit - when entering a limit price, the average execution price is identical to the indicated price.
2. Range - when entering price range, the cost basis for the specified range is equal to the geometric mean of the highest and lowest price boundaries of the indicated range.

GeometricMean=(minPrice)∗(maxPrice)GeometricMean=(minPrice)∗(maxPrice)​

**Budget aspect**

Budget indicates the amount of tokens allocated to each order. This is a base value that will be used against the indicated price mentioned above.

**100% fill calculation**

Using the values from [`Price`](https://faq.carbondefi.xyz/mechanics/order-execution/100-fill-estimation#price-aspect) \* [`Budget`](https://faq.carbondefi.xyz/mechanics/order-execution/100-fill-estimation#budget-aspect) results in the estimated 100% fill value.

#### Notice <a href="#notice" id="notice"></a>

As orders within a recurring strategy are traded against and refilled, 100% fill estimation results may change.
