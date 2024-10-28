# Limit Orders and Automated Strategies

Alien Base users have access to advanced tools for creating automated strategies (i.e. strategies that execute automatically based on certain predefined conditions or triggers). These tools are provided thanks to the deep integration of [Carbon](https://www.carbondefi.xyz/), an innovative DEX technology created by the Bancor team.&#x20;



{% embed url="https://video.twimg.com/ext_tw_video/1824582331761315840/pu/vid/avc1/1280x720/1U9WNZjYfhcpDIVa.mp4?tag=12" %}
Alienbase v1.2 intro video
{% endembed %}

### What are Alien Base's automated strategies?

The technology borrowed from Carbon consists in an orderbook-style DEX allowing users to perform novel trading strategies with all standard ERC20 tokens\* using a variety of order types:

* [**Limit Order**](limit-orders.md) - A single disposable buy or sell order at a specific price
* [**Range Order**](range-orders.md) - A single disposable buy or sell order within a custom price range
* [**Recurring Orders**](recurring-orders.md) - buy and sell orders (limit or range) that are linked together, and perform similar to grid trading or a DEX trading bot. Newly acquired funds automatically rotate between them, creating an endless trading cycle without need for manual intervention

By design, Carbon DeFi's limit, range, and recurring orders are all irreversible on execution, easily adjustable, resistant to MEV sandwich attacks, fully on-chain, non-custodial and can be deployed with any standard ERC20 token.

There are two key market participants in the automated strategies:

1. “Makers” submit automated strategies composed of one or two on-chain limit or range orders.
2. “Takers” perform “spot” trades against live strategies directly, via DEX aggregators, or as arbitrageurs. Spot trading requests are handled by way of a decentralized SDK or using any custom software capable of processing the on-chain data.

Makers are similar to liquidity providers in normal automated market makers (AMMs) in that their activities support the liquidity of the system in an on-chain, permissionless manner. However, they are notably different in that each maker can customize their own personalized spread or "fee tier" between their buy and sell ranges. This is in contrast to existing AMMs which force liquidity providers to adopt the fee of the AMM they're providing liquidity to.

### What are the main benefits?

The technology used for Alien Base's automated strategies differs from what common in AMMs in the following ways:

1. Adjustable Fee: Users who provide liquidity ("makers") can set a specific buy range and a specific sell range for their tokens, which establishes a custom fee/spread, instead of all makers having to adopt the fee that is prescribed by the AMM.
2. Rotating Liquidity: Liquidity is automatically moved between the maker's selected buy/sell ranges as orders are executed.
3. Irreversible Orders: User liquidity trades in one direction, irreversibly.
4. MEV Resistance: Spot trading is protected from MEV sandwich attacks.

#### Adjustable Fee <a href="#adjustable-fee" id="adjustable-fee"></a>

Users who create automated strategies on Alien Base ("makers") are similar to liquidity providers in existing AMMs in that their activities supply liquidity for trading, and they collect fees from other users ("takers") who perform spot trades using their liquidity.

However, the system is unique in that each individual maker can customize the fee they collect from trades - i.e., the difference between their selected buy and sell ranges. While legacy AMMs force their liquidity providers to adopt the fee of the AMM they're providing liquidity to,  you can set your own personalized fee (or spread) by selecting the specific price(s) where you'd like to buy and sell your tokens.

#### Rotating Liquidity <a href="#rotating-liquidity" id="rotating-liquidity"></a>

When a user provides liquidity in existing on-chain liquidity protocols/AMMs, their position buys and sells tokens using a single pricing curve ("bonding curve").

On Alien Base's automated strategies, each user position consists of two bonding curves (or "orders") - one for buying and one for selling. When a user deposits a token pair, each token in the pair has one custom curve based on settings decided by the user. Once your position buys or sells at your desired price, your liquidity is automatically rotated to its paired curve, and vice versa.

In the case of a single-use limit or range order, as the order is executed, liquidity is taken "off-curve" and shifted to an inactive paired order, where it sits idle until the maker withdraws their position.

In the case of a recurring strategy, buy and sell orders trade in perpetuity, and liquidity continuously shifts between the paired orders as trades are executed, until the user chooses to stop the strategy. Such a strategy offers to buy in one price range and sell in a higher range akin to a "Grid Trading" or "Scalping" strategy.

#### Unidirectional, Irreversible Orders <a href="#unidirectional-irreversible-orders" id="unidirectional-irreversible-orders"></a>

In normal concentrated liquidity like Alien Base V3, executed orders may be reversed when markets retrace. This is due the bidirectional nature of AMM liquidity: Once a buy order for one asset is traded against, a sell order for the other asset is placed at the same price. To avoid order reversal, users must manually monitor and withdraw their liquidity upon execution (or rely on external tooling to do so).

In contrast, limit/range orders flow in a single direction and are therefore irreversible on execution. This removes the need for users to constantly monitor their orders and manually withdraw in time, or rely on a third-party to do so. [Read more about limit orders](limit-orders.md)[.](https://medium.com/carbondefi/true-dex-limit-orders-carbon-vs-existing-solutions-58cd955098fd)

#### MEV Protection <a href="#mev-protection" id="mev-protection"></a>

Due to the irreversibility of automated orders, spot trades that execute against these automated strategies are protected from MEV sandwich attacks.
