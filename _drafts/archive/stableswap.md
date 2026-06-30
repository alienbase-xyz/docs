---
description: Deprecated Saddle-style stableswap pools
---

# StableSwap (deprecated)

**Status:** deprecated. No longer surfaced in the dApp's primary UI.

> *Last updated: {{today}}.*

## What it was

StableSwap was Alien Base's deployment of Saddle-style (Curve-derived) stablecoin AMM pools, listed as a separate protocol on DefiLlama. It was designed for low-slippage swaps between same-asset variants (e.g., stablecoin↔stablecoin, ETH↔cbETH, BTC↔cbBTC).

It launched as one of several attempts to specialize liquidity for tightly-pegged assets without forcing them through a generic V2 or V3 pool. In practice, it never gained meaningful TVL — Alien Base V3 supports dedicated low fee tiers (0.01% / 0.02% for stables, 0.03% / 0.04% for LSDs and very-blue-chip volatile pairs, 0.075% for ETH/BTC) which serve the same use case more efficiently and with better composability.

## Why it was deprecated

- TVL never grew to a level that justified maintenance overhead.
- V3 with the 0.01% / 0.02% / 0.03% / 0.04% / 0.075% fee tiers handles the same pairs more efficiently.
- DefiLlama still lists "Alien Base StableSwap" as a separate protocol entry, but the pools have minimal current activity and aren't featured in Alien Base's UI.

## Contracts

<!-- TODO:USER -->Confirm the StableSwap deployment addresses (pools, factory, gauge if any). The original Medium roadmap announcement of StableSwap should have these; we'll cross-reference and add to the [Contracts — Deprecated section](../contracts.md).

## If you have funds in StableSwap

Pools remain on-chain and remain functional. To withdraw:

1. Identify the specific StableSwap pool you deposited into.
2. Call `removeLiquidity(...)` (or `remove_liquidity_one_coin` for single-asset withdrawal in Saddle-style pools) on the pool contract directly via Basescan.
3. If your LP is staked, `withdraw(...)` from the gauge / farm first.

If you can't figure it out, post in [Discord](https://discord.gg/alienbase) — the team can walk you through it.

## See also

- [Contracts — Deprecated section](../contracts.md)
- [V3 — fee tiers](../liquidity/v3.md#fee-tiers) — the active replacement for stable / LSD pools.
