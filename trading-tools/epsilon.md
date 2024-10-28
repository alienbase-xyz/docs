# Epsilon

Epsilon is Alien Base's _meta-aggregator_ system: the aggregator of aggregators.

Whenever you make a swap on Alien Base, Epsilon will look for the most convenient rate across all integrated DEXs and aggregators, including for tokens that are not natively available on Alien Base.

While Epsilon prioritizes native Alien Base pools, it can be used to trade any asset on Base, as long as it's available on one of the supported DEXs and aggregators.

Currently, in addition to Alien Base, Epsilon supports the following aggregators and DEXs:

| Name      | Category   |
| --------- | ---------- |
| OpenOcean | Aggregator |
| ParaSwap  | Aggregator |
| Uniswap   | DEX        |
| SushiSwap | DEX        |
| Aerodrome | DEX        |

Epsilon features a small front-end fee for trades that are not native to Alien Base pools or its tokens. The fee is equal to:

* 0.03% for stablecoins, ETH and BTC
* 0.16% for all other assets

In the vast majority of cases, the fee will be significantly less than the efficiency savings from using Epsilon.
