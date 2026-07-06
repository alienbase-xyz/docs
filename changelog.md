---
description: Public, dated record of what shipped on Alien Base
---

# Changelog

A public, dated record of what shipped on Alien Base, source-cited where possible.

> *Last updated: July 6, 2026.*

## 2026

### July — Trading terminal + Epsilon Router launch

Full app redesign around a professional **trading terminal**: TradingView chart, chain-wide token search, position tracking (Balances / Open orders / Active DCAs / Closed orders / Trades), and a trending ticker — all on [app.alienbase.xyz/swap](https://app.alienbase.xyz/swap).

The **Epsilon Router** ([`0x303c…2580`](https://basescan.org/address/0x303ca5c65AabCb1CE242DF93F478c41E0E4D2580), audited) goes live, bringing order execution on-chain and shipping new order types: **Limit / Take Profit / Stop Loss / Stop Buy**, **Trailing Stop**, and upgraded **DCA** with trigger prices and stop-loss aborts. Order fees are tiered by asset class — see [Fees](fees.md).

The **Vaults** page is redesigned around named strategies (Wide / Narrow / Ultra Narrow / Classic V3) with three tabs: Vaults, Locked earn (esALB + esLP staking), and Legacy farms. A **Dashboard** page aggregates positions, earnings, and rewards per wallet.

Carbon-powered Limit / Range / Recurring orders are **deprecated** in favor of the Router order system; existing Carbon orders remain visible from the Dashboard and withdrawable on-chain. See [Archive — Carbon Orders](archive/carbon-orders.md).

### April — Alien Base 2.0 (AIP-5) approved

[AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) passes (Yes 42.63 M / No 0.36 M / abstentions 0.05 M). Replaces farming with a Protocol-Owned-Liquidity (POL) Fund + buyback-and-burn. Replaces fixed halvings with flexible emissions. Introduces Dev Line of Credit, govALB (10× voting, 2-year lock), and a one-time supply-cap raise from 510 M → 1.051 B ALB. Splits governance between the Alien Base DAO (onchain) and Alien Labs (offchain). Onchain rollout begins immediately.

### March — Alien Base 2.0 design preview

Long-form preview article: [Alien Base 2.0 — Building Sustainable Tokenomics for Long-Term Growth](https://medium.com/@alienbase/alien-base-2-0-building-sustainable-tokenomics-for-long-term-growth). Sets the stage for the AIP-5 vote.

### January — Vaults page launches

The Vaults page replaces the legacy Farms tab. Unifies V3 / Bunni positions and esALB / esLP staking. Introduces Zap-in flow for one-click LP creation and a Claim All button across positions.

Mothership repo gets its `audit-scope` commit (see [audits.md](audits-and-security.md)).

## 2025

### October — Roadmap retrospective

[Alien Base Roadmap: Plotting the Next Phase of the Invasion](https://medium.com/@alienbase/alien-base-roadmap-plotting-the-next-phase-of-the-invasion-11ede525e2ea). Confirms the third halving (June 2025) cut yearly inflation from ~30% to ~15%. Reaffirms Mothership and Project Quasar as the next priorities; explicitly classifies the B3 multi-chain deployment as not having delivered.

### August — Foundation operating budget (ADIP-01)

[ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) passes — first proposal authored by "Alienbase Foundation (Proposed)". Sets the six-month operating budget (Sept 2025 → Feb 2026): $200k USDC reserve + $42.5k revenue-funded growth + 1M ALB/month dev allowance + 1M ALB/month POL contribution.

Three small community-led proposals also pass in early August: YouTube channel access, Pilot Video Production (Alienbase Academy), and an Academy thread chat channel.

### June — Third halving + AIP-4

Yearly inflation drops from ~30% to ~15% as the third halving fires. [AIP-4](https://snapshot.org/#/alienbase-dex.eth/proposal/0x3e1f7e1841389638f6fda99baefd61331cf711fdc7f4649ad96713c25a747826) passes; community chooses "Prioritize DAO" over "Prioritize holders". Authorizes additional multi-year vested allocations and foreshadows the dev-company structure later formalized as Alien Labs.

`VestingFactory` deployed and team allocations vested through it.

### May — Epsilon Analytics launches

The Explore page goes live. GoPlus-powered safety checks per token. Per-pool charts. Wallet activity views.

### Early year — multi-chain B3 deployment

Alien Base ships on B3 chain (deployment of an isolated V2 fork), announced January 31, 2025 as "our first multi-chain deployment", supporting the B3 token launch of February 10, 2025. The deployment was later flagged as having underperformed expectations and is no longer a strategic focus — see [Archive — B3](archive/b3.md).

## 2024

### December — Alien Foundation established

The Cayman-registered ownerless legal entity is set up. See [Alien Foundation](alien-base-dao/alien-foundation.md).

### November — All-time high

ALB hits **$0.572** on November 27, 2024. Lifetime high to date.

### October — AIP-3

[AIP-3](https://snapshot.org/#/alienbase-dex.eth/proposal/0x2f8f7d71af345928b7d0040553aa8f923c21865d2cd0bee226e3a12626b654fc) passes. Establishes the second-halving DAO budget. Dev team transfers 33% of its emissions rights to the DAO (DAO collection rate 15% → 20%). Dev operational allowance raised 600k → 1M ALB/month. By this proposal, >60% of circulating ALB was already locked as esALB.

### September — Second halving

Emissions drop from 7.5 → 3.75 ALB/sec.

### April — esALB launches

[Introducing EsALB](https://medium.com/@alienbase/introducing-esalb-the-next-phase-of-alien-base-tokenomics-e5bfa049486f). Single-staking, governance, Real Yield. Initial reception was strong — esALB became the central long-term holder primitive on Alien Base.

### March 26 — Token Generator

The Token Generator MVP launches (orchestrator [`0xBcE7…d08d`](https://basescan.org/address/0xBcE75497D72b25c3509B62ae1a47CCfb502AD08d) deployed on-chain March 26, 2024). Simple / Mintable / Burnable / Mint+Burn / Tax templates. 0.015 ETH fee per mint.

## 2023

### November — V3 launch + AIP-2

V3 (concentrated liquidity) ships. [AIP-2](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52) passes (Yes 14.35 M / No 0). Establishes the 50% team / 40% holders / 10% DAO-treasury revenue split. Boosts emissions to 10.5 ALB/sec for two months. Authorizes 2 M ALB for V3 launch incentives. Sets up the DAO Multisig (now 5-of-8 at [`0x4ab9070b…71e5`](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5)).

### September — Roadmap update

[Strategic Roadmap Update for Alien Base](https://medium.com/@alienbase/strategic-roadmap-update-for-alien-base-c569f2bfcc46). First public projection of where Alien Base would go after the V2 launch.

### August 19 — AIP-1 (de facto)

Sniper bots had captured the launch liquidity, leaving real circulating supply ~1 M instead of the planned 26 M. [The first Snapshot vote](https://snapshot.org/#/alienbase-dex.eth/proposal/0x56c418fd7f7fd365b0beba44389807941e3150fb376179ac758fb497f04a999b) passes (Yes 7,127 / No 15) and emissions drop from 15 → 8 ALB/sec via the 7-day-delayed `updateEmissionRate()` flow.

### August 8 — Token Generation Event

Alien Base launches V2 (Uniswap V2-style AMM) on Base with 26 M ALB initial mint, of which 1 M seeds the launch LP. The remaining 25 M is sent to a timelock for staged release.

The original [Welcome to Alien Base](https://medium.com/@alienbase/welcome-to-alien-base-7ed4dc5da9a3) article is published.

---

## What's not in this changelog

Day-to-day frontend updates (UI tweaks, copy changes, partner-token list updates) and infrastructure work (RPC, indexers, etc.). These are tracked internally and called out in Discord; the changelog is for protocol-level changes worth a long-tail mention.
