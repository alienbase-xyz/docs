---
description: One page for every yield-bearing position on Alien Base
---

# Vaults overview

The **Vaults** page is the central UI surface for every yield-bearing position you hold on Alien Base — V3 (Bunni-wrapped) liquidity, V2 LP staking, esALB and esLP single-stake, and (soon) Mothership-managed positions.

> *Last updated: {{today}}.* Vaults launched January 2026, replacing the legacy Farms tab.

## What's on the Vaults page

| Vault type | What it does | Where the underlying liquidity sits |
| --- | --- | --- |
| **V3 Vault** | Static-range V3 LP wrapped as an ERC-20 by Bunni. Earn pool fees + ALB rewards. | Uniswap-V3-style pools on Alien Base |
| **esALB Single Stake** | Stake esALB to earn unlocked ALB + Real Yield (WETH). | Stake-only contract; no AMM exposure |
| **esLP** | Lock LP tokens (e.g., ALB-ETH) for boosted ALB rewards + Real Yield. | V2 pools |
| **V2 Farm (legacy)** | Stake unlocked V2 LP tokens for ALB rewards. | V2 pools |
| **Mothership Vault** *(coming)* | Actively-managed multi-range V3 positions. | V3 pools, dynamically rebalanced by Mothership strategies |

## Key UI features

- **Zap-in.** One-click flow that takes a single asset (e.g., ETH or USDC), splits it appropriately, and creates the LP position in a single transaction. Removes the "swap, then add liquidity, then stake" three-step dance.
- **Claim All.** Single button to harvest rewards across every active position in one transaction.
- **Filtered views.** Filter by status (active, no rewards, retired), by risk profile (stable, blue chip, mid cap), or by reward type.
- **APR breakdown.** Each card shows pool APR, ALB-emission APR, and Real Yield (WETH) APR separately, plus the all-in total.

## How a Vault deposit flows

1. Connect wallet.
2. Pick the Vault you want to enter.
3. Click **Deposit** (or **Zap**).
4. Choose the asset and amount.
5. Approve (one-time per token) → confirm the deposit.
6. Position appears in the My Positions section. Rewards start accruing immediately.

## V3 / Bunni Vaults

Most "Vault" entries on the page are static-range V3 LP positions wrapped by Bunni. The wrapping turns the V3 NFT position into an ERC-20 share token, which:

- Lets the protocol farm the position (you can stake an ERC-20 in a normal MasterChef-style farm; you can't easily stake an NFT).
- Lets you transfer or use the position elsewhere (composability).
- Adds a single, predictable price range per Vault (no per-user range selection).

Range design:

- **Wide ranges** consider up to 2 years of price history; designed to stay in range for another 1–2 years.
- **Narrow ranges** are more aggressive; can go out of range in weeks-to-months on volatile assets.
- **Stable / LSD ranges** are very tight — for cbETH, the range accounts for ~2 years of staking yield.

When a range gets close to its bounds, a new Vault is deployed with refreshed bounds. Old Vaults remain available so existing depositors can decide whether to migrate.

For more detail: [Bunni explainer](bunni.md).

## Concentrated Liquidity (raw V3)

For LPs who want full control — pick your own range, fee tier, manage rebalancing manually — Alien Base also exposes the raw V3 interface. See [Concentrated Liquidity (V3)](v3.md).

## V2 Pools

V2 pools are still active (~$281K total ALB-ETH liquidity at time of writing) and remain the primary venue for ALB itself. See [V2 Pools (legacy)](v2-pools.md).

## Open items

- <!-- TODO:USER -->Add a screenshot of the current Vaults page once the AIP-5 rollout settles.
- <!-- TODO:USER -->List the currently-active Vaults with their full APR breakdown — this should ideally be auto-generated from a backend feed rather than hand-listed.

## See also

- [Concentrated Liquidity (V3)](v3.md)
- [Bunni explainer](bunni.md)
- [V2 Pools (legacy)](v2-pools.md)
- [Mothership](mothership.md) — the upcoming actively-managed Vault layer.
- [esALB Single Stake](../escrowed-alb-esalb/README.md#staking-esalb)
