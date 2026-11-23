---
description: What to do when your V3 / Bunni position drifts outside its range
---

# My LP is out of range

Concentrated-liquidity positions only earn fees while the market price is **inside** the price range you (or the Vault) configured. When price exits the range, the position holds 100% of one asset and earns nothing until either price returns or you reposition.

This is normal and expected — concentrated liquidity is a trade-off — but it has a few wrinkles worth knowing.

> *Last updated: July 6, 2026.*

## How to tell

On the [Vaults](https://app.alienbase.xyz/vaults) or Liquidity page, an out-of-range position is flagged:

- **🟡 Out of range** badge on the position card.
- The asset breakdown shows ~100% of one token, ~0% of the other.
- The "Fees earned in last 24h" stat is ~0.

## What's actually happening

Imagine you set an ETH/USDC range from $2,800 to $3,200, and the market is at $3,000.

- While ETH is between $2,800 and $3,200, your position swings between holding more USDC (when price is high) and more ETH (when price is low). It earns fees on every trade in your range.
- If ETH moves to $3,500 (above your range), your position is 100% USDC. You "sold" your ETH on the way up, at progressively better prices, and now you're holding USDC. You earn no fees until ETH comes back to $3,200.
- If ETH moves to $2,500 (below your range), your position is 100% ETH. You "bought" ETH on the way down, at progressively better prices. No fees until ETH comes back to $2,800.

Importantly: this isn't a "loss" in the sense of money disappearing. You hold the same total value as a passive holder, minus impermanent-loss-style asymmetry — sometimes more, sometimes less, depending on price path. What you've lost is the **opportunity** of earning fees.

## Your three options

### 1. Wait for price to come back

If the price excursion is small and short-lived (the asset drifts a bit out of range, then mean-reverts), waiting is fine. You re-engage when price returns to your range.

### 2. Withdraw and re-deposit at a new range

For raw V3 positions: remove liquidity, swap to balance, redeposit at a fresh range. Two transactions plus the gas to swap. Expensive on Ethereum; tractable on Base.

For Bunni Vaults: most Vaults have a fixed range. If a particular Vault is consistently out of range, the protocol typically deploys a new Vault with refreshed bounds — migrate to it.

### 3. Let an active manager handle it

[Mothership](../liquidity/mothership.md) is exactly this — an automated liquidity manager that re-balances ranges as price moves. Once Mothership goes live, deposit there instead of into a static-range Vault.

## When to choose what

- **Stable / LSD pairs (USDC/USDT, ETH/cbETH).** Out of range is rare. Static ranges work fine.
- **Blue chip pairs (ETH/USDC, BTC/ETH).** Wide static ranges work fine; expect occasional repositioning during big moves.
- **Mid-cap / volatile.** Static ranges are high-effort. Wait for Mothership, or use V2 instead (full-range, no range management).
- **Memecoins.** Concentrated liquidity is mostly the wrong tool. Use V2.

## The math behind it

Capital efficiency in V3 scales roughly with how narrow your range is, but so does your risk of being out of range. A range that captures a 2× price move is much more capital-efficient than full-range — but if price moves 3×, you're stuck on one side.

Two practical heuristics:

- **Volatility-based range.** Set the range to ~2× the recent annualized volatility on either side of the current price. Lets price swing within a normal volatility window without exiting.
- **Time-based range.** Set the range to capture the price band you expect over the holding period. Wider for longer holds.

Neither is perfect. The honest answer is: predicting price ranges is hard, which is why ALMs (Mothership) exist.

## See also

- [Concentrated Liquidity (V3)](../liquidity/v3.md)
- [Vaults overview](../liquidity/vaults.md)
- [Bunni explainer](../liquidity/bunni.md)
- [Mothership](../liquidity/mothership.md) — the active-management answer.
- [V2 Pools (legacy)](../liquidity/v2-pools.md) — when concentrated liquidity is the wrong tool.
