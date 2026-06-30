---
description: Discontinued price-prediction game
---

# Predictions (discontinued)

**Status:** discontinued. No longer offered.

> *Last updated: {{today}}.* <!-- TODO:USER confirm exact discontinuation date and any contract details users need for stranded funds. -->

## What it was

A short-window price-prediction game inspired by PancakeSwap's Predictions feature. Users would bet ETH (or another asset) on whether the price of an asset would be higher or lower at the end of a fixed round (typically 5 minutes). Winners shared the round's pot pro-rata.

It was a fun engagement product but not a core part of Alien Base's value proposition. Maintenance and game-balance overhead exceeded the activity it generated, and the team chose to wind it down to focus on the trading and liquidity products.

## Contracts

<!-- TODO:USER -->List the on-chain Predictions contracts that were used (e.g., a `PredictionETH` contract — on-chain analysis suggests one was deployed by the team deployer). Even though the game is no longer surfaced, users should be able to verify the contract and confirm there are no unclaimed winnings.

## If you have unclaimed winnings

If you participated and never claimed:

1. Find your address's Predictions transactions on Basescan.
2. Call `claim(...)` on the deployed Predictions contract directly.

If you need help, post in [Discord](https://discord.gg/alienbase).

## See also

- [Lottery (discontinued)](lottery.md) — the other engagement-focused product that was sunset.
- [Roadmap](../roadmap.md) — what the team is building instead.
