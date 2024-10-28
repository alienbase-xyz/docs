# Order Dynamics

### Marginal Price <a href="#marginal-price" id="marginal-price"></a>

Marginal price indicates the order "best" price at the moment, which is also the starting price for any trader to interact with.

#### Example: <a href="#example" id="example"></a>

1. User creates a strategy between ETH/USDC:
   1. Sell 100 ETH between 1650-1700 USDC
   2. Buy ETH with 10,000 USDC budget between 1590-1640 USDC
2. On creation, the "Marginal price" would be:
   1. Sell marginal price is **1650 USDC** as this is the starting price for traders
   2. Buy marginal price is **1640 USDC** as this is the starting price for traders
3. A trader interacted with the Sell order and took 20 ETH from the order
   1. Sell marginal price will change from 1650 USDC to **1659 USDC** (as it is slowly moving to 1700 USDC)
   2. A trader took additional 30 ETH from the order
   3. Sell marginal price will change from 1659 USDC to **1674 USDC**
4. A trader now interacts with the Buy order and gave it 10 ETH (in return for USDC)
   1. Buy marginal price will change from 1640 USDC to **1631 USDC** (as it is slowly moving to 1590 USDC)

### Partial Fill <a href="#partial-fill" id="partial-fill"></a>

Partial fill represents a case in which the order budget is only partial used.

On the strategy overview card, there are two colors:

* Solid color - represents price range area that still has budget
*   Carbon DeFi moai logo coloring - represents price range area that was used and taken by traders

    ![](https://faq.carbondefi.xyz/\~gitbook/image?url=https%3A%2F%2F2154147289-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fgv7qaob2jiuF6yZxRK9C%252Fuploads%252FFjwvV8TfAuXAd1HGF82p%252Fimage.png%3Falt%3Dmedia%26token%3D149ff22f-4c77-413e-93d0-f3008471941b\&width=768\&dpr=4\&quality=100\&sign=2c95e25f\&sv=1)

Example:

1. User creates a strategy between ETH/USDC:
   1. Sell 100 ETH between 1650-1700 USDC
   2. Buy ETH with 10,000 USDC budget between 1590-1640 USDC
2. A trader interacted with the Sell order and took 20 ETH from the order
   1. Results in Sell order partial filled as it still holds 80 ETH (out of the initial 100 ETH)

### Fulfilment Dynamics <a href="#fulfillment-dynamics" id="fulfillment-dynamics"></a>

At some cases, you might see that the market price indication will be "in the money" but no trader is willing to interact with the order. This can happen if the cost of trade is greater than the arbitrage opportunity.

Example:

* Market price is at 1641 USDC per ETH
* Sell ETH order between 1635-1645 USDC (indicating the order is "in the money")
* Available liquidity between 1635-1641 USDC is 0.0001 ETH

Result:

The available liquidity is not sufficient to make the trade profitable.
