---
description: Index of every passed proposal in the Alien Base DAO
---

# AIP Index

A complete index of every Alien Base governance proposal voted on at [`alienbase-dex.eth`](https://snapshot.org/#/alienbase-dex.eth) on Snapshot.

> *Last updated: {{today}}. 9 proposals total. All passed; none failed; none currently active.*

| # | Date (UTC) | Title | State | Result | Tag |
| --- | --- | --- | --- | --- | --- |
| (de facto AIP-1) | 2023-08-19 | [Reduce ALB Emissions by 46% for the Remaining Distribution Period](https://snapshot.org/#/alienbase-dex.eth/proposal/0x56c418fd7f7fd365b0beba44389807941e3150fb376179ac758fb497f04a999b) | passed | Yes 7,127 vs No 15 | tokenomics |
| AIP-2 | 2023-11-24 | [Emission schedule and tokenomics improvements](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52) | passed | Yes 14.35 M vs No 0 | tokenomics + governance |
| AIP-3 | 2024-10-07 | [Establishing DAO Budget for 2nd Halving Cycle](https://snapshot.org/#/alienbase-dex.eth/proposal/0x2f8f7d71af345928b7d0040553aa8f923c21865d2cd0bee226e3a12626b654fc) | passed | Yes 37.24 M vs No 0 | treasury |
| AIP-4 | 2025-06-02 | [Empowering DAO & Optimizing Spending for Next Halving Cycle](https://snapshot.org/#/alienbase-dex.eth/proposal/0x3e1f7e1841389638f6fda99baefd61331cf711fdc7f4649ad96713c25a747826) | passed | Prioritize DAO 71.14 M vs Prioritize holders 0.45 M | tokenomics + treasury |
| (no AIP #) | 2025-08-01 | [Grant Ben Access to Youtube Channel](https://snapshot.org/#/alienbase-dex.eth/proposal/0xca9bb55e6d793ec78044049df40b8f415c7ef729ae35e6717187c26f5d1b3a52) | passed | For 39.0 M | community |
| (no AIP #) | 2025-08-01 | [Pilot Video Production — Alienbase Academy](https://snapshot.org/#/alienbase-dex.eth/proposal/0x5ef5e5a25c213cd6b679c315a0d32245f5a4644aa1babab04d53a8f2a93c7684) | passed | For 38.96 M vs Against 1.82 | treasury (community) |
| (no AIP #) | 2025-08-01 | [Alienbase Academy Thread Chat Channel](https://snapshot.org/#/alienbase-dex.eth/proposal/0x19ae49a6bcce493d55870f9aa9aadd62664f3d5a99c9fef709376a06532916b8) | passed | For 39.41 M vs Against 1.82 | governance (community) |
| ADIP-01 | 2025-08-28 | [6-Month Operating Budget and Treasury Strategy](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) | passed | For 19.19 M | treasury |
| AIP-5 | 2026-04-07 | [Building Alien Base 2.0](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63) | passed | Yes (as is) 42.63 M; Keep halvings 0.36 M | tokenomics + roadmap |

## Proposal summaries

### AIP-1 — Emission emergency cut (2023-08-19)

Eleven days after launch, sniper bots had captured the intended initial liquidity-pool seed, leaving real circulating supply ~1 M instead of the planned 26 M and producing ~600% first-week relative inflation. The proposal cut emissions from **15 → 8 ALB/sec** (–46%) via a `prepareFunction()` then a 7-day-delayed `updateEmissionRate()` on the `DistributorController`. Although the proposal isn't titled "AIP-1", it is the chronological first DAO vote and established the AIP numbering used by everything since.

### AIP-2 — V3 launch + tokenomics improvements (2023-11-24)

Four-part proposal timed to the V3 (concentrated-liquidity) launch:

1. Raise emissions from 8 → 10.5 ALB/sec for two months before tapering.
2. Authorize up to **2 M ALB** from the DAO treasury at `0xD9c14E5A…cC4d` for a targeted V3 boost (ETH/USDC, tBTC/ETH, ALB pools).
3. Establish a uniform **50% team / 40% holders (Single-Stake + esALB) / 10% DAO-treasury** revenue split for both Alien Base and Area 51.
4. Spin up the **DAO Multisig** (now `0x4ab9070b…71e5`) with a 50/50 team-vs-top-holder structure.

### AIP-3 — 2nd halving cycle DAO budget (2024-10-07)

Sets the DAO operating budget for the period after the second halving (Sep 2024, when emissions dropped from 7.5 → 3.75 ALB/sec). Key changes:

- Dev team transfers 33% of its emissions rights to the DAO → **DAO collection rate rises from 15% to 20%** (~1,944,000 ALB/mo).
- The remaining 66% of the dev team's emissions earmarked for **long-term vested positions** for DAO contributors, devs, and potential external investors.
- Dev operational allowance raised from **600k → 1.0M ALB/month** to cover salaries and infrastructure.

By this proposal, **>60% of circulating ALB was already locked as esALB** and **~50% of trade fee revenue** was being redistributed to esALB holders.

### AIP-4 — Empowering DAO & Optimizing Spending (2025-06-02)

Halving-cycle proposal coinciding with the third halving (June 2025, ~30% → 15% yearly inflation). Highlights:

- An esALB-style **multi-year additional lock** vesting over close to 5 years total since launch.
- A plan to fund a "development company behind Alien Base" via the DAO under a standard R&D contract (foreshadowing what AIP-5 later formalized as Alien Labs).
- An expected ~8% drop in esALB APR at then-current revenue levels.

The community chose the "**Prioritize DAO**" variant (71.14M for, 0.45M for "Prioritize holders").

### August 2025 community proposals

Three smaller proposals authored by an active community member (`0x2360…E704`, also a DAO Multisig signer) all passed:

- **YouTube channel access** ($0 budget) for community member "Ben" to upload videos and maintain playlists.
- **Pilot video production** ($300 USDC) for a 3–5 minute educational video on the DCA feature, produced by Nathan.
- **Academy thread chat channel** ($0 budget) for ongoing peer-led Q&A and lectures.

These set a precedent for low-stakes operational proposals being decided by the DAO without requiring an AIP-format full proposal.

### ADIP-01 — 6-Month Operating Budget (2025-08-28)

The first **"ADIP" (Alienbase DAO Improvement Proposal)** — distinct from AIPs in that it's authored by the **Alienbase Foundation (Proposed)** rather than by an individual address. Adopts and incorporates AIP-4's terms.

Sets a six-month hybrid budget (Sept 2025 → Feb 2026):

- **$200,000 USDC reserve**: Infrastructure $48k / Liquidity & Incentives $40k / Strategic Savings $112k.
- **$42,500 revenue-funded growth**: Dev & Security $15k, Legal $12.5k, Marketing $10k, Grants $5k.
- Treasury also holds 37,000,000 ALB; net ~4M ALB deficit covered by reserves.
- Authorizes 1M ALB/month dev allowance and 1M ALB/month POL contribution.

### AIP-5 — Building Alien Base 2.0 (2026-04-07)

Full tokenomics rewrite. Replaces farming with a **Protocol-Owned-Liquidity (POL) Fund** and replaces fixed halvings with flexible emissions + persistent buyback-and-burn. Introduces:

- **Dev Line of Credit (LoC):** the dev allowance becomes tracked debt with interest paid to esALB holders. Price-tier grant tranches at $0.40, $1, and $2 unlock as ALB sustains those moving averages.
- **govALB:** new staked-escrow form of esALB with 10× voting power, 1× earning power, ~2-year effective lock.
- **Supply cap raised** (one-time): **510,000,000 → 1,051,000,000 ALB**. Direct allocation increase = 200M; remainder reserved for esALB protection program and strategic allocations. Expected actual supply post-rollout ≤ 800M.
- **Governance split** between Alien Base DAO (onchain contracts) and Alien Labs (offchain product/frontend/revenue).

The minority dissent (0.36 M for "keep halvings") is the only non-zero "no" vote in the project's history.

## Author concentration

Of nine proposals to date:

- `0xdD8B…0A390` (a founder-style address): 3 proposals — AIP-1 (de facto), AIP-2, AIP-5.
- `0xF277…20e9`: 2 proposals — AIP-3, AIP-4.
- `0x2360…E704` (also a DAO Multisig signer): 4 proposals — the three Aug 2025 community items + ADIP-01.

The transition from a single founder voice to multiple authors and finally to a "Foundation (Proposed)" voice mirrors the protocol's gradual decentralization.
