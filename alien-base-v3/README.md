# Alien Base V3

The Uniswap V3 architecture is the most flexible DEX out there, since it can support any kind of asset with maximum efficiency. It can be used for stablecoins, loosely pegged assets like cbETH, blue chips like ETH and BTC, or very volatile tokens like memecoins.

Higher efficiency means that you need less money to support a particular level of trade slippage, and the tighter the ranges, the more efficient it becomes.

Alien Base's V3 supports the following fee tiers:

| Fee    | Best for              |
| ------ | --------------------- |
| 0.02%  | Stablecoin pairs      |
| 0.075% | Blue chips (ETH, BTC) |
| 0.30%  | Mid-cap tokens        |
| 1%     | Small-cap tokens      |

**Static Farming Ranges**

Alien Base V3 is powered by a fork of Bunni, a liquidity management system developed by [Timeless Finance](https://timelessfi.com/).

Bunni is very simple: it enables to create vaults for a particular V3 range and fee tier, which creates an ERC-20 share token just like a regular V2 position.

Farmable ranges are defined by past volatility and price history.&#x20;

The **Wide** ranges consider up to 2 years of previous price history to come up with safe ranges for another 1-2 years. **Narrow** vaults are more aggressive, and may go out of range in the next few weeks to months (depending on the asset).

Finally, some assets like stablecoins or LSDs can have very concentrated ranges with nearly no impermanent loss. For example, on cbETH the range accounts for 2 years of staking yield.

If a particular range is close to its limits, new ones will be deployed to enable a more balanced LP position.

\
\
\
\
