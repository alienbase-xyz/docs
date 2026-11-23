---
description: Discontinued price-prediction game
---

# Predictions (discontinued)

**Status:** discontinued. No longer offered.

> *Last updated: July 6, 2026.* <!-- TODO:USER confirm exact discontinuation date and any contract details users need for stranded funds. -->

## What it was

A short-window price-prediction game inspired by PancakeSwap's Predictions feature. Users would bet ETH (or another asset) on whether the price of an asset would be higher or lower at the end of a fixed round (typically 5 minutes). Winners shared the round's pot pro-rata.

It was a fun engagement product but not a core part of Alien Base's value proposition. Maintenance and game-balance overhead exceeded the activity it generated, and the team chose to wind it down to focus on the trading and liquidity products.

## Contracts

The `PredictionETH` contract, deployed by the AlienBase Deployer, is at [`0xFBE87Ee1…63e8`](https://basescan.org/address/0xFBE87Ee1Ee62244A2dF80a8093Eab829C52863e8) (verified source). Even though the game is no longer surfaced in the dApp, you can verify the contract and claim any unclaimed winnings directly from the explorer's Write tab.

## If you have unclaimed winnings

If you participated and never claimed:

1. Find your address's Predictions transactions on Basescan.
2. Call `claim(...)` on the deployed Predictions contract directly.

If you need help, post in [Discord](https://discord.gg/alienbase).

## See also

- [Lottery (discontinued)](lottery.md) — the other engagement-focused product that was sunset.
- [Roadmap](../roadmap.md) — what the team is building instead.
