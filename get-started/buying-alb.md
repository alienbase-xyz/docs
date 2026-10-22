---
description: How to acquire ALB on Base
---

# Buying ALB

ALB is the native token of Alien Base. The fastest path to acquire it is on Alien Base itself — but several other venues also have ALB liquidity.

> _Last updated: October 22, 2026._

{% hint style="warning" %}
**There are two ALB contracts right now.** The **new ALB** (`0x1b23…cef7`) is the canonical token after the [Alien Base 2.0 migration](../migration/README.md). The **legacy ALB** (`0x1dd2…50C4`) still trades and can be migrated 1:1 at any time. Check the address before you buy.
{% endhint %}

## On Alien Base (recommended)

1. Have ETH on Base. (See [Bridging to Base](bridging-to-base.md) if you don't.)
2. Go to [app.alienbase.xyz/swap](https://app.alienbase.xyz/swap).
3. Sell ETH (or USDC, or any token you have on Base) → buy ALB. Make sure the token you select is the **new ALB** (`0x1b23…cef7`).
4. Epsilon will route your trade through whichever pool gives the best price.

New ALB pools: ALB/WETH ([`0xFF43…F1B7`](https://basescan.org/address/0xFF4364b623dC4D9A1556774467748EAb68DfF1B7)) and ALB/USDC ([`0x4867…c97d`](https://basescan.org/address/0x48676681A1F5BefD4b79273BdA2D85cD5390c97d)) on Alien Base V3.

While holders migrate, most liquidity may still sit in **legacy ALB** pools such as the legacy V3 ALB-WETH pool ([`0xbcd27A43…6fcB`](https://basescan.org/address/0xbcd27A437eBe92555Cee6b5bBeDdAC639a1b6fcB)). If legacy ALB is the better deal, you can buy it and [migrate it 1:1](../migration/README.md) to new ALB. For a guided walkthrough, see [Swap](../trading/swap.md).

## On other DEXes

Legacy ALB also has pools on:

* **Uniswap** (3 pools as of July 6, 2026)
* A few smaller venues

If you're already on one of those DEXes, ALB will be swappable there. But Epsilon will give you the best price by aggregating across all of them, so trading on Alien Base directly is almost always better.

## What address to use

Always verify the contract address before swapping:

* **ALB (new, canonical):** [`0x1b23704e3f4bc7081fb00cec582183e3fe43cef7`](https://basescan.org/token/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7)
* **ALB (legacy, migrates 1:1):** [`0x1dd2d631c92b1aCdFCDd51A0F7145A50130050C4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4)

Both are named "ALB", so the symbol alone tells you nothing. Beware of scam tokens with similar names, and of anyone offering to "migrate" your tokens outside [app.alienbase.xyz/migration](https://app.alienbase.xyz/migration). If you paste an address into the token selector, double-check it matches one of the above.

## What to do with ALB after buying

Most users do at least one of:

1. **Lock it as esALB** to earn ALB rewards + Real Yield automatically. See [esALB](../escrowed-alb-esalb/).
2. **Provide liquidity** in V3 / Bunni Vaults (infinite or concentrated, capital-efficient). See [Vaults](../liquidity/vaults.md).
3. **Vote** on Snapshot proposals once locked as esALB. See [Alien Base DAO](../alien-base-dao/).

## Tracking ALB

* [**Dune dashboard**](https://dune.com/sealaunch/alienbase) — canonical, includes ALB price, supply, esALB lock state, holders, top pairs.
* [CoinGecko](https://www.coingecko.com/en/coins/alienbase) — price and market cap.
* [DexScreener (new ALB)](https://dexscreener.com/base/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7) · [DexScreener (legacy ALB)](https://dexscreener.com/base/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) — every pool, every trade.
* [Supply API](../alb-token.md#supply-api) — live total and circulating supply of new ALB.
* [DefiLlama](https://defillama.com/protocol/alien-base-v3) — TVL across the protocol.
* [GeckoTerminal](https://www.geckoterminal.com/) — alternative pool view.
* Inside Coinbase Wallet, search "ALB" to add to watchlist.

Full data-source map: [Data & Analytics](../data-and-analytics.md).
