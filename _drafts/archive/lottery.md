---
description: Discontinued on-chain lottery
---

# Lottery (discontinued)

**Status:** discontinued. No longer offered.

> *Last updated: {{today}}.* <!-- TODO:USER confirm exact discontinuation date and any contract details users need for stranded funds. -->

## What it was

A periodic on-chain lottery where users bought tickets in ALB (or ETH; <!-- TODO:USER confirm -->) and a randomized draw distributed the pot to winners. The product borrowed from PancakeSwap's lottery design and aimed to drive engagement and ALB demand.

Like Predictions, it was an engagement product rather than a core trading or liquidity feature. The team deprecated it to focus operational bandwidth on Mothership, Epsilon Router, and the Alien Base 2.0 rollout.

## Contracts

<!-- TODO:USER -->List the deployed Lottery contract address (on-chain analysis indicates an `AlienbaseLottery` contract was deployed by the team deployer). Users should be able to verify and call into it directly if they have unclaimed positions.

## If you have unclaimed tickets / winnings

If you participated and never redeemed:

1. Find your address's Lottery-related transactions on Basescan.
2. Call the appropriate `claim` function on the Lottery contract.

If you need help, post in [Discord](https://discord.gg/alienbase).

## See also

- [Predictions (discontinued)](predictions.md)
- [Roadmap](../roadmap.md)
