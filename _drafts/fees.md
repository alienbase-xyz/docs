---
description: Single source of truth for every fee on Alien Base
---

# Fees

This page lists every fee charged anywhere on Alien Base, what it pays for, and where the value flows.

> *Last updated: {{today}}.*

## TL;DR

- Alien Base charges **no buy/sell taxes** on the ALB token.
- Liquidity providers earn pool fees directly. **esALB stakers** earn a share of protocol fees as **Real Yield in WETH** and other liquid assets.
- The platform itself takes only what's needed to fund the operating budget approved by the DAO.

## At a glance

| Product | Fee | Where it goes |
| --- | --- | --- |
| **V2 swap** | **0.16%** | LPs |
| **V3 swap** | **7 fee tiers** (see below) | **50% LPs / 50% esALB stakers** |
| **Epsilon** front-end fee (non-native pools) | **0.03%** stables / ETH / BTC, **0.20%** everything else | Treasury / esALB |
| **Carbon** orders (Limit / Range / Recurring) | **0.40%** on the trade, on top of the maker's spread | Treasury / esALB |
| **DCA** orders | Same schedule as Epsilon — **0.03%** blue chips / **0.20%** other | Treasury / esALB |
| **Token Generator** | **0.015 ETH** per token mint | Operating budget |
| Liquidity ops (add / remove / claim) | None | — |
| Locking ALB → esALB | None | — |
| Unlocking esALB → ALB | None | — |

## Trading fees

### V2 swaps

- **0.16% per swap** in standard V2 pools, paid by the taker.
- **Distribution:** flows to LPs in-pool. The V2 Factory's `feeToSetter` is the DAO Multisig — the protocol-side carve-out can be enabled and routed to the protocol share by DAO vote.

### V3 (Concentrated Liquidity) swaps

V3 uses fee tiers. Each pool is created with a fixed tier:

| Tier | Best for |
| --- | --- |
| **0.01%** | Tightly-pegged stablecoin pairs (USDC/USDbC, USDC/USDT) |
| **0.02%** | Standard stablecoin pairs |
| **0.03%** | LSDs and very-blue-chip volatile pairs (ETH/cbETH) |
| **0.04%** | Wider-spread stable / LSD pairs |
| **0.075%** | Blue chips (ETH, BTC and wrapped variants) |
| **0.30%** | Mid-cap and standard tokens |
| **1.00%** | Small-cap and memecoin pairs |

The wide tier ladder lets each pool choose the fee that matches its volatility. Tighter pegs use the lower tiers; volatile pairs use the higher tiers.

**Distribution:** **50% to LPs** in-pool, **50% to esALB stakers** as Real Yield. esALB Real Yield is paid in WETH (and select underlying tokens / stablecoins).

### Epsilon front-end fee (non-native pools)

When [Epsilon](trading/epsilon.md) routes a trade through pools outside Alien Base (e.g., Aerodrome, Uniswap, PancakeSwap, SushiSwap), a small front-end fee is added on top of the underlying pool fees. There is **no Epsilon fee on Alien Base's own pools**.

| Asset class | Fee |
| --- | --- |
| Blue chips (stables, ETH, BTC and wrapped variants) | **0.03%** |
| Everything else | **0.20%** |

In nearly every case the fee is significantly less than the price improvement Epsilon captures by aggregating the entire chain.

**Distribution:** routed to the Treasury, with the bulk going to the esALB Real Yield stream.

### Carbon orders (Limit / Range / Recurring)

Alien Base's Limit, Range, and Recurring orders are powered by Bancor's Carbon technology. They behave like irreversible on-chain market-maker positions.

- **Maker.** When you create a Limit, Range, or Recurring order, you implicitly define a **spread** between your buy and sell prices. That spread is your margin and you keep all of it.
- **Alien Base fee.** **0.40% on the executed trade**, on top of the maker's spread. Routed to the Treasury / esALB Real Yield stream.
- **Gas.** Takers pay gas at fill time. Makers pay gas only at order creation, edit, and withdrawal.

A maker's all-in revenue per filled order is therefore: their spread minus the 0.40% Alien Base fee on the executed trade.

### DCA orders

DCA orders use the same fee schedule as Epsilon — each DCA chunk is a swap, so it pays Epsilon-equivalent fees:

| Asset class | Fee per DCA chunk |
| --- | --- |
| Blue chips (stables, ETH, BTC) | **0.03%** |
| Everything else | **0.20%** |

Plus the underlying swap fee from whichever pool Epsilon routes the chunk through.

**Required input asset:** WETH (raw ETH must be wrapped first; the DCA UI surfaces this as an inline warning).

**Distribution:** routed to the Treasury / esALB Real Yield stream.

## Liquidity provision

There are no fees to add or remove liquidity beyond gas. Specifically:

- **No deposit fees** on V2 farms (the deposit-fee parameter is permanently set to zero post-launch).
- **No withdraw fees** on farms.
- **No performance fee** on Bunni-wrapped V3 positions.

Vaults that auto-compound (Bunni and future Mothership-managed vaults) collect fees inside the AMM pool and increase the LP token's redemption value over time; there is no on-claim performance fee taken at the vault layer. <!-- TODO:USER -->Confirm whether Mothership will charge a manager fee + performance fee at launch.

## ALB locking & vesting

- **Locking ALB → esALB:** free. 1:1.
- **Unlocking esALB → ALB:**
  - 30-day full unlock: free, no penalty. Vested position continues to earn at a 30%-reduced APR until redemption.
  - 1% every 12 hours: free, instant.
  - Redemption window: 7 days after the 30-day vesting completes — if not claimed in 7 days, the position auto-relocks for another 30 days.
- **Vesting (multi-year):** the AIP-4 / VestingFactory streams have no user-facing fee; they are an internal accounting facility for team / DAO contributors.

## Token Generator

- **Deployment fee:** **0.015 ETH per token**, regardless of template.
- The fee is paid in ETH at deploy time and is non-refundable.
- The deployment fee funds the operating budget; an explicit per-template breakdown is not maintained.

If your generated token uses the **Tax** template, your token's own buy/sell taxes are independent of any Alien Base fee — the Tax token implements its own taxation logic, payable to the addresses you set.

## Where the protocol's share goes

Per **AIP-3** and **ADIP-01**, the protocol's share of fees (V3 50% staker share, Epsilon front-end, Carbon 0.40%, DCA, Token Generator) flows to:

1. **Real Yield to esALB holders** in WETH and protocol tokens — this is the largest line.
2. **DAO operating budget** (audits, infrastructure, marketing, legal, dev allowances) — set as a USDC and ALB allocation per cycle, not as a percentage.
3. **Protocol-Owned Liquidity (POL)** — building treasury liquidity that earns yield → buyback-and-burn ALB (ramping under [AIP-5](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63)).

The current cycle's specific dollar allocations are defined in [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) and refreshed every six months by DAO vote.

## Historical fee changes

| Date | Change | Source |
| --- | --- | --- |
| 2023-08-08 | Launch with **0.16% V2 swap fee**. | [Roadmap for Aliens](https://medium.com/@alienbase/the-roadmap-for-aliens-c84a86d337cc) |
| 2023-11-27 | V3 launches with concentrated-liquidity fee tiers; AIP-2 establishes the LP / staker fee-sharing structure (originally 60/40, later normalized to 50/50). | [AIP-2](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52) |
| 2024-Q3 | Carbon Limit / Range / Recurring orders launch. | [Carbon DeFi blog](https://www.carbondefi.xyz/blog/alien-base-is-the-first-to-integrate-bancor-technologies-directly-into-its-dex) |
| 2024-Q4 | Real Yield in WETH activated for esALB stakers. | [AIP-3](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd) |
| 2024-11 | Epsilon adds Odos with a **0% Epsilon fee promo** for an initial period. | [Epsilon Upgrade](https://medium.com/@alienbase/epsilon-upgrade-odos-integration-and-introduction-to-epsilon-analytics-66b779bf9912) |
| 2025-06 | Third halving — yearly inflation cut 30% → 15%; fee structure unchanged. | [AIP-4](https://snapshot.org/#/alienbase-dex.eth/proposal/0x3e1f7e1841389638f6fda99baefd61331cf711fdc7f4649ad96713c25a747826) |
| 2026-04 | AIP-5 ratifies replacing fixed halvings with flexible emissions + persistent buybacks. | [AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) |
| Current | V2 0.16% · V3 7 tiers (0.01–1.00%) at 50/50 LP/esALB · Epsilon 0.03%/0.20% · Carbon 0.40% · DCA same as Epsilon | this page |

## Open items

- <!-- TODO:USER -->Confirm exact date the V3 share moved from 60/40 (AIP-2 original) → 50/50 (current). Was this an explicit later proposal, an executive change by the DAO Multisig, or did the AIP-2 implementation always settle at 50/50?
- <!-- TODO:USER -->Confirm exact date the V3 fee tier ladder expanded from 4 tiers (0.02 / 0.075 / 0.30 / 1.00) to 7 tiers (added 0.01 / 0.03 / 0.04). Was it part of the AIP-5 rollout?
- <!-- TODO:USER -->Confirm exact date the Carbon 0.40% Alien Base fee was introduced (early Carbon docs framed it as "0% Alien Base fee — maker keeps the spread").
- <!-- TODO:USER -->Confirm exact date DCA fees moved from a flat 0.1% to the Epsilon-mirroring 0.03% / 0.20% schedule.
