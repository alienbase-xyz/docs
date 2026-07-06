---
description: The original Alien Base AMM — Uniswap V2 fork
---

# V2 Pools (legacy)

V2 pools are the original Alien Base liquidity venue. Built on Uniswap V2 contracts, launched at TGE in **August 2023**.

> _Last updated: July 6, 2026._

## When to use V2

* **Trading any pair you can't (or won't) actively manage.** V2 is constant-product (`x * y = k`) — no ranges, no concentrated liquidity, no out-of-range states.
* **Memecoins and small caps.** V2 is forgiving of price discovery and has the simplest LP UX.
* **Set-and-forget LPing.** No active management, no rebalance, no out-of-range risk.

## Mechanics

* **50/50 deposit.** You provide both tokens in equal value at the current price.
* **Full-range exposure.** Your liquidity is active across every price point, from zero to infinity.
* **Pool fee.** **0.16%** per swap, paid by the taker and distributed to LPs. The V2 Factory's `feeToSetter` is the DAO Multisig — the protocol-side carve-out can be enabled by DAO vote.
* **LP token.** Standard ERC-20. Stakeable, transferable, farmable.

## Where to find them

* **Trade.** The [trading terminal](https://app.alienbase.xyz/swap) routes through V2 automatically when it's the best venue.
* **LP.** **New position** (on the [Vaults](https://app.alienbase.xyz/vaults) or Dashboard page) → select **V2** — add or remove V2 liquidity directly.
* **Farm.** The old V2 farms live under **Vaults → Legacy farms**; their emissions have wound down under AIP-5, so the tab is mainly for unstaking. See [Vaults](vaults.md#legacy-farms-tab).

## Why "legacy"?

By using a Bunni wrapper set to an infinite range, we can achieve the same effective impact of a traditional V2 position. Because of that, V2 vaults have been gradually deprecated over the years.

## See also

* [Concentrated Liquidity (V3)](v3.md) — the higher-efficiency alternative.
* [Vaults overview](vaults.md)
* [Token Generator](../tools-for-projects/token-generator/) — the easiest path from "I have an idea" to "my token has a V2 pool".
* [Contracts](../contracts.md) — V2 Factory, Router, Farm addresses.
