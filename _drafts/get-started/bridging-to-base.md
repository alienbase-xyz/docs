---
description: Move ETH or assets from Ethereum (or other chains) onto Base
---

# Bridging to Base

To use Alien Base you need ETH on **Base**. This page covers the canonical and third-party bridging options.

> *Last updated: {{today}}.*

## TL;DR

- **From Ethereum mainnet:** Coinbase Wallet's built-in bridge or [bridge.base.org](https://bridge.base.org). Native, secure, slow on the way back.
- **From any other chain:** any reputable cross-chain bridge that supports Base. Faster but introduces a third-party trust assumption.
- **From a Coinbase account:** Coinbase exchange supports direct withdrawal to Base. The fastest path for most users.

## Native bridge (Ethereum ↔ Base)

The official Base bridge is at [bridge.base.org](https://bridge.base.org). Run by Coinbase, with no third-party intermediaries:

- **Deposits (Ethereum → Base):** ~1–10 minutes. Costs Ethereum gas.
- **Withdrawals (Base → Ethereum):** ~7-day challenge period before funds release on Ethereum. This is a property of how OP-stack rollups work, not an Alien Base or Base-specific delay.

Best for: large amounts you want to move with the lowest possible trust assumptions.

## Coinbase exchange direct withdrawal

If you already have an account on Coinbase, you can withdraw ETH directly to your wallet on Base. No bridge required. Fastest path for most users.

1. On Coinbase, choose Withdraw → ETH.
2. Network: **Base**.
3. Destination: your wallet address.

## Coinbase Wallet built-in bridge

If you use Coinbase Wallet (browser extension or mobile), the in-app bridge handles Ethereum → Base in a single flow. UX is significantly smoother than going to bridge.base.org manually.

## Third-party bridges

For chains other than Ethereum (or for users who want faster Base → Ethereum exits), use a reputable bridge. Common options that support Base:

- Across
- Stargate
- Synapse
- Hop Protocol
- LI.FI / Squid (cross-chain aggregators)

Each one has its own trust model and fees — read the docs before using a bridge with significant capital. <!-- TODO:USER endorse a specific subset if Alien Base has preferred / partner bridges -->

## What you need

- **Some ETH on Base for gas.** Even ~$1 worth is enough for many transactions.
- **The token you want to trade**, if it's not already available on Base. If a token only exists on Ethereum (or another chain), you'll need to bridge it specifically; bridging ETH alone won't bring your other tokens.

## After bridging

Once your funds are on Base, head to [Connecting your wallet](connecting-your-wallet.md) and then [Buying ALB](buying-alb.md) (or any other token you want to trade).

## Common issues

- **"Stuck deposit."** Deposits from Ethereum to Base take a few minutes. If yours is taking longer than 30 minutes, check the transaction on [Etherscan](https://etherscan.io/) — if it confirmed, the funds are on Base. The bridge just hasn't updated its UI.
- **"Withdrawal not showing on Ethereum."** If you used the native bridge (bridge.base.org), there's a 7-day challenge period. This is normal.
- **"Wrong network in wallet."** Most wallets auto-suggest switching to Base when you visit Alien Base. If yours doesn't, manually add Base (chain id 8453) — see [Connecting your wallet](connecting-your-wallet.md).
