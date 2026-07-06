---
description: "Deprecated: Carbon-powered Limit, Range, and Recurring orders"
---

# Carbon Orders (Limit / Range / Recurring)

> **Status: deprecated (July 2026).** Replaced by the [Epsilon Router](../trading/epsilon.md#the-epsilon-router) order system — Limit, Take Profit, Stop Loss, Trailing Stop, and DCA. Existing Carbon orders remain visible from your Dashboard and stay withdrawable on-chain.

> *Last updated: July 6, 2026.*

## What it was

From 2024 to mid-2026, Alien Base's resting orders were powered by Bancor's **Carbon DeFi** technology — Alien Base was the first DEX to integrate Carbon directly. The suite included:

- **Limit Orders** — one-time orders at a single price.
- **Range Orders** — one-time orders distributed across a price range, filling incrementally.
- **Recurring Orders** — paired buy + sell sub-orders that rotated automatically, like an on-chain grid-trading bot. Proceeds from a filled side rotated into the other side until withdrawn.

Carbon orders behaved like irreversible on-chain market-maker positions: the user was a **maker** defining a spread, and takers (aggregators, arbitrageurs) filled against them. They were MEV-resistant by construction — the order's irreversibility prevented sandwich attacks at fill time — and charged a 0.40% Alien Base fee on executed trades.

## Why it was deprecated

The Epsilon Router brought order execution in-house and unlocked order types Carbon couldn't express (trailing stops, stop-loss DCA, trigger-price DCA), with execution routed through Epsilon's meta-aggregation for best price at fill time. Running two parallel order systems added surface area without adding capability, so Carbon order creation was retired with the July 2026 trading terminal upgrade.

The trade-off: Epsilon Router orders are executed by the Matcher at market route (with slippage tolerance), whereas Carbon fills were zero-slippage maker fills. Users who specifically want maker-style, spread-capturing strategies can still provide concentrated liquidity via [Vaults](../liquidity/vaults.md).

## If you still have open Carbon orders

- Open orders remain visible in your **Dashboard**.
- Funds stay in the CarbonController contract ([`0xe376…716e`](https://basescan.org/address/0xe3763886bf91d5466b416b37fdf2b6337897716e)) — non-custodial, withdrawable at any time.
- A legacy interface for managing (or creating) Carbon orders may be made available; check the Discord announcements. <!-- TODO:USER confirm whether the legacy Carbon UI link ships, and add the URL -->

## See also

- [Limit, Take Profit & Stop Loss](../trading/limit-orders.md) — the replacement for Limit / Range orders.
- [DCA Orders](../trading/dca-orders.md) + [Trailing Stop](../trading/trailing-stop.md) — the replacement for automation strategies.
- [Contracts](../contracts.md) — CarbonController address.
