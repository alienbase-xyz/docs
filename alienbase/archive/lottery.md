---
description: Discontinued on-chain lottery
---

# Lottery (discontinued)

**Status:** discontinued. No longer offered.

> *Last updated: July 6, 2026.* <!-- TODO:USER confirm exact discontinuation date and any contract details users need for stranded funds. -->

## What it was

A periodic on-chain lottery where users bought tickets in ALB and a randomized draw distributed the pot to winners. <!-- TODO:USER confirm ticket currency (ALB or ETH) --> The product borrowed from PancakeSwap's lottery design and aimed to drive engagement and ALB demand.

Like Predictions, it was an engagement product rather than a core trading or liquidity feature. The team deprecated it to focus operational bandwidth on Mothership, Epsilon Router, and the Alien Base 2.0 rollout.

## Contracts

The `AlienbaseLottery` contract, deployed by the AlienBase Deployer, is at [`0x4384DCF9…48Ff`](https://basescan.org/address/0x4384DCF974769F2E0E52cdE92b6D5fC9be5248Ff) (verified source). If you have unclaimed positions, you can call the contract's claim functions directly from the explorer's Write tab.

## If you have unclaimed tickets / winnings

If you participated and never redeemed:

1. Find your address's Lottery-related transactions on Basescan.
2. Call the appropriate `claim` function on the Lottery contract.

If you need help, post in [Discord](https://discord.gg/alienbase).

## See also

- [Predictions (discontinued)](predictions.md)
- [Roadmap](../roadmap.md)
