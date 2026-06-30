---
description: What's shipping next on Alien Base
---

# Roadmap

Alien Base's mission is to be the human-friendly trading hub on Base — a meta-DEX that aggregates the entire chain's liquidity behind a CEX-quality interface, with custom protocols built on top to push capital efficiency further than any single DEX could.

> *Last updated: {{today}}.*
> *For what already shipped, see the [Changelog](changelog.md). This page focuses on what's coming.*

## Right now

The active build cycle is the **Alien Base 2.0** rollout authorized by [AIP-5](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63) (April 2026). The team is shipping the new tokenomics and the next product layer in parallel:

| Workstream | Status | What's in it |
| --- | --- | --- |
| **Mothership** (ALM) | Pre-launch — audit in flight, alpha imminent | Custom-built Automated Liquidity Manager. First "from-scratch" Alien Base protocol. Multi-range V3 management with strategy-plugin architecture. Public alpha launches with strict supply caps. |
| **Epsilon Router** (on-chain aggregator) | Audited, report under review | Moves Epsilon routing from off-chain APIs to on-chain contracts. Unlocks native order types: stop loss, trailing stop, stop-loss DCA, and more. |
| **Alien Base 2.0 tokenomics** | Onchain rollout in progress (Apr–May 2026) | POL Fund, Dev Line of Credit, govALB token, raised supply cap. See [ALB Token](alb-token.md#alien-base-2-0-aip-5). |
| **Vaults** | Live since Jan 2026 | Replaces the old Farms tab; unifies legacy V3 / Bunni positions and (future) Mothership-managed vaults. Adds Zap flow + Claim All. |
| **Epsilon Analytics** | Live since May 2025 | Chain-wide Explore page, GoPlus-powered token safety checks, per-pool charts. |

## Q3–Q4 2026

Themes for the rest of 2026 (subject to DAO and operating-budget refresh):

- **Mothership Beta** — wider access, multiple strategies, strategy marketplace where third-party LP managers earn fees on user capital.
- **Token Generator v2** — comprehensive launchpad with fair-launch tooling. Replaces and extends the current Token Generator MVP.
- **Analytics & Visualization Revamp** — TradingView integration with order overlays + PnL tracking. Deeper Epsilon Analytics insights including wallet-cluster analysis (multi-wallets per user, bot detection, whale activity, team-sell detection).
- **Automated esALB reward distribution** — modular fee payouts to esALB stakers, designed to plug into future ALM expansions.
- **Migration of remaining team-controlled contracts** to the DAO Multisig — see the [onchain control surface](audits-and-security.md#onchain-control-surface) for which contracts are still team-owned.

## Bigger horizons

Alien Base has consistently set ambitious long-term targets. The list below is honest about which ideas are active engineering and which are research / vision.

| Idea | Status | Notes |
| --- | --- | --- |
| **Mothership marketplace** | Active engineering | "Marketplace of liquidity managers": third-party strategists publish strategies, attract user capital, earn fees. The Mothership architecture was designed for this from day one. |
| **Project Quasar** (lending / IL options) | Research / on hold | Originally pitched as the next product after V3; deprioritized in favor of Mothership and Epsilon Router. Reaffirmed in the [Oct 2025 roadmap](https://medium.com/@alienbase/alien-base-roadmap-plotting-the-next-phase-of-the-invasion-11ede525e2ea) for "2025+" but no shipped artifacts. |
| **Project Nebula** (next-gen AMM) | Long-term vision | The original "everything in one AMM" vision: 50× concentrated liquidity, single-sided LP, no forced 50/50 split, instant liquidity for derivatives. No active engineering yet; will follow Mothership maturity. |
| **Multi-chain expansion** | On hold | The 2025 B3 deployment was [explicitly classified as not having delivered](https://medium.com/@alienbase/alien-base-roadmap-plotting-the-next-phase-of-the-invasion-11ede525e2ea) in the Oct 2025 retro. The team is now more cautious about high-investment cross-chain partnerships. |

## What we're not building

A short list of things we've explicitly decided against — not because they don't exist on Earth, but because they don't fit Alien Base's strategy:

- **Yet-another-launchpad** detached from a DEX. Token Generator v2 is integrated with the trading and liquidity stack, not a standalone fundraising venue.
- **Inflationary-only farming as a long-term mechanism.** AIP-5 retired the fixed-halving farming model in favor of POL + buyback-and-burn.
- **A copy-paste perp DEX.** Project Quasar is the leveraged-trading thesis, but only in a form that uses LP capital efficiently (impermanent-loss-as-options) — not as a generic GMX/dYdX clone.

## How decisions get made

Major direction shifts happen via Snapshot proposal in the [`alienbase-dex.eth`](https://snapshot.org/#/alienbase-dex.eth) space. Anyone holding 100,000+ ALB can submit a proposal; see [How to Propose](alien-base-dao/how-to-propose.md). The full history of past votes is on the [AIP Index](alien-base-dao/aip-index.md).

For day-to-day product priorities, the team posts updates on [Discord](https://discord.gg/alienbase) and longer-form articles on [Medium](https://medium.com/@alienbase).
