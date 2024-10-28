# Strategy ROI

Automated Strategies are designed to allow traders to set a recurring buy high / sell low trading strategy on chain. Given this ability, it is possible to calculate each strategy's returns (ROI) using the information provided from strategy actions such as creation, balance changes and trades that interact with the available liquidity.

#### Disclaimer <a href="#disclaimer" id="disclaimer"></a>

The aim is to calculate an ROI figure that is most intuitive to the user based on their performance using the automated strategies.

We use a method that utilizes only the current prices of paired tokens, applied historically to every block, and evaluates the returns as a percentage of the liquidity provided.

#### Calculating ROI <a href="#calculating-roi" id="calculating-roi"></a>

In order to calculate the strategy ROI, we use the following rules:

1. Only trade events affect the calculation. This means that add/remove liquidity actions will not cause the ROI value to change.
2. We use "sub-strategies" to calculate strategy ROI. Sub-strategies are the times between each balance changing action (add/remove liquidity).
3. The strategy ROI is the sum of all the sub-strategy returns (USD) divided by the total liquidity amount deposited (evaluated in USD), provided that the liquidity has been traded with.
4. We use the current USD price of the tokens to calculate "sub-strategy" returns using the historical token amounts against the current USD price.

In order to calculate the ROI, we use this process:

1. Calculate the token gains for every sub-strategy
2. Multiple the token amounts with their current market price to USD
3. Sum the gains USD value and divide it by the strategy value

```
Example:
Start
1 ETH and 1 WBTC
1 ETH @ $2,000 USD = $2,000         # uses the current price today
1 WBTC @ $40,000 USD = $40,000      # uses the current price today
Total value of portfolio is $42,000

The user's order is partially traded against, converting their ETH for WBTC.

End 
0.5 ETH and 1.05 WBTC
0.5 ETH @ $2,000 USD = $1,000        # uses the current price today
1.05 WBTC @ $40,000 USD = $42,000    # uses the current price today
Total value of portfolio is $43,000

Returns: $43,000 - $42,000 = $1,000
ROI: returns / value deposited = 1,000/42,000 = 2.38%
```
