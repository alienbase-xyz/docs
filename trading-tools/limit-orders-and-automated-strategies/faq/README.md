# FAQ

### How do I create a limit order?

Head on the [Swap](https://app.alienbase.xyz/swap) page, select Limit. Select a pair, a price or a price range in which you would like the order to get filled ([more on range orders](../range-orders.md)) and create the strategy. When the price of the selected token reaches the predefined price or price range, the market will take the order if profitable ([more on order execution](order-execution.md))

### Will money be taken from my wallet?

Yes, Alien Base's automated strategies are true limit orders, i.e. creating a strategy is similar to providing liquidity on Alien Base v3 in a specific price range and fee tier. The difference is that the fee tier is decided by the buy low/sell high spread, and the order is irreversible.

### How do I modify/delete my order?

Head on the [Dashboad](https://app.alienbase.xyz/liquidity) where you can see all your active automated strategies. For each active strategy, you can edit prices, deposit new funds, withdraw funds, delete.

### Will the strategy delete itself after filling the order?

No. Limit orders on Alien Base are not just an execution of a pre-approved trade at a trigger price with an expiry. Once you create a limit order you created a full automated strategy, so it will stay active. Once you have an active strategy for a pair, you can modify it the way you want, even from normal limit order to recurring order.

### Will I automatically receive the money in my wallet?

No. Each strategy is funded the same way LPs add liquidity on the dex. Even if the order is filled, the funds will stay in the "pool" until you withdraw them (or delete the strategy, which is the same thing)

#### For any doubts or questions, open a ticket on [Discord](https://discord.com/channels/1151515107587792896/1151602990860484618)
