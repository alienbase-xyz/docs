---
description: How to acquire ALB on Base
---

# Buying ALB

ALB is the native token of Alien Base. The fastest path to acquire it is on Alien Base itself — but several other venues also have ALB liquidity.

> *Last updated: {{today}}.*

## On Alien Base (recommended)

1. Have ETH on Base. (See [Bridging to Base](bridging-to-base.md) if you don't.)
2. Go to [app.alienbase.xyz/swap](https://app.alienbase.xyz/swap).
3. Sell ETH (or USDC, or any token you have on Base) → buy ALB.
4. Epsilon will route your trade through whichever pool gives the best price — almost always one of Alien Base's native ALB pools.

The deepest market is the V2 ALB-WETH pool ([`0xbcd27A43…6fcB`](https://basescan.org/address/0xbcd27A437eBe92555Cee6b5bBeDdAC639a1b6fcB)). For a guided walkthrough, see [Swap](../trading/swap.md).

## On other DEXes

ALB also has pools on:

- **Uniswap** (3 pools as of {{today}})
- **Aerodrome**
- **SwapBased**
- A few smaller venues

If you're already on one of those DEXes, ALB will swap there. But Epsilon will give you the best price by aggregating across all of them, so trading on Alien Base directly is almost always better.

## What address to use

Always verify the contract address before swapping:

- **ALB:** [`0x1dd2d631c92b1aCdFCDd51A0F7145A50130050C4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4)

Beware of scam tokens with similar names. The Alien Base swap UI loads the canonical token by default; if you paste an address into the token selector, double-check it matches the one above.

## What to do with ALB after buying

Most users do at least one of:

1. **Lock it as esALB** to earn single-stake APR + Real Yield. See [esALB](../escrowed-alb-esalb/README.md).
2. **Provide liquidity** in V2 (full-range, simple) or V3 / Bunni Vaults (concentrated, capital-efficient). See [Vaults](../liquidity/vaults.md).
3. **Vote** on Snapshot proposals once locked as esALB. See [Alien Base DAO](../alien-base-dao/README.md).

## Tracking ALB

- **[Dune dashboard](https://dune.com/sealaunch/alienbase)** — canonical, includes ALB price, supply, esALB lock state, holders, top pairs.
- [CoinGecko](https://www.coingecko.com/en/coins/alienbase) — price and market cap.
- [DexScreener](https://dexscreener.com/base/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) — every pool, every trade.
- [DefiLlama](https://defillama.com/protocol/alien-base-v3) — TVL across the protocol.
- [GeckoTerminal](https://www.geckoterminal.com/) — alternative pool view.
- Inside Coinbase Wallet, search "ALB" to add to watchlist.

Full data-source map: [Data & Analytics](../data-and-analytics.md).
