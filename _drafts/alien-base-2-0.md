---
description: The AIP-5 tokenomics rewrite, in plain language
---

# Alien Base 2.0

**Alien Base 2.0** is the package of tokenomics and governance changes authorized by [AIP-5](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63) (passed April 2026). It replaces the old "halving farming model" with a new model built around Protocol-Owned Liquidity, a Dev Line of Credit, and a clearer DAO / Foundation / Labs split.

> *Last updated: {{today}}.* Onchain rollout is in progress. This page tracks the moving pieces.

## The five changes at a glance

1. **Farming → POL.** Farming emissions wind down. A Protocol-Owned-Liquidity (POL) Fund takes over as the primary liquidity-provision mechanism.
2. **Halvings → flexible emissions.** The old fixed-halving schedule retires. Emissions are sized to revenue, with headroom kept on the upside if needed.
3. **Dev allowance → Line of Credit.** Team funding becomes tracked debt with interest paid back to esALB holders. Price-tier grants at $0.40, $1, $2 unlock as ALB sustains those moving averages.
4. **govALB.** New staked-escrow tier with **10× voting power**, 1× earning power, ~2-year effective lock.
5. **Supply cap raised.** One-time bump from **510,000,000 → 1,051,000,000 ALB**. Direct allocation increase = 200M; remainder reserved for esALB protection program and strategic allocations. Expected actual supply post-rollout: ≤ 800M.

## Why each piece matters

### POL Fund

Farming subsidies are the most expensive form of liquidity a protocol can buy. Every block, the protocol prints ALB and gives it to LPs. As the price recovers, the LPs typically sell — extracting value from the protocol.

The POL Fund flips this:

- The DAO holds the liquidity itself (stablecoins, blue chips, Base-native assets, Alien Base LPs).
- Yield from POL is used for **buyback-and-burn ALB**.
- Net result: liquidity stays on the platform, ALB supply grows more slowly (or shrinks during high-volume periods), and the protocol keeps the value its trading volume generates.

### Flexible emissions

Halvings were a clean concept but rigid. They didn't respond to market conditions, treasury health, or demand. AIP-5 replaces them with **emissions that scale with protocol revenue** and that can be adjusted via governance more dynamically. Emissions never run away because they're capped by supply.

### Line of Credit

Treasury-to-team funding was previously a flat allowance — emit X ALB/month for the dev budget. Two issues:

- It was static. If ALB price 10x'd, the dev team got 10x the funding regardless of need.
- It was untracked. There was no formal accounting of what the DAO had funded.

The Line of Credit fixes both. Every ALB drawn for dev funding is **tracked debt**. esALB holders receive interest on the outstanding LoC — projected ~30–35% APR at expected operating volumes. Debt clears via **price-tier grants**: when ALB sustains $0.40, $1, or $2 (moving averages), a tranche unlocks as a grant rather than debt. This aligns Labs's funding with protocol value creation.

### govALB

esALB is great for one-eyed governance ("my voice matters" while my ALB is locked) — but it's still relatively short-term commitment. Many of the protocol's biggest decisions (tokenomics, multi-year roadmap) deserve input from holders with longer time horizons.

govALB is the long-time-horizon tier. **10× voting weight** in exchange for a roughly 2-year effective lock. Earning rate stays 1× — govALB doesn't print extra rewards, just amplifies governance weight.

### Supply cap raise

The old 510M cap was set in 2023 and has been ~90% emitted. Rather than letting issuance crash to zero (and starving the protocol of incentives at the moment Mothership and Epsilon Router go live), the cap is raised once to 1.051 B.

Important: the cap is a **ceiling**, not a target. The expected actual supply post-rollout is **≤ 800 M**. The 200 M direct allocation increase covers the next phase of growth; the remainder is reserved for the **esALB protection program** (preserving APR for esALB holders during the transition) and **strategic allocations** (POL seeding, partner integrations, future grants).

## DAO / Foundation / Labs split

AIP-5 also formalized the org structure:

- **Alien Base DAO** — the on-chain authority. Holds privileged roles on the protocol contracts. Ratifies major decisions via Snapshot.
- **[Alien Foundation](alien-base-dao/alien-foundation.md)** — Cayman-registered, ownerless legal entity. Holds offchain assets (USDC reserves, vendor relationships, audit engagements). Acts on behalf of the DAO when an offchain counterparty is required.
- **[Alien Labs](alien-base-dao/alien-labs.md)** — operational arm. Builds the dApp, designs and ships products, runs commercial operations. Funded via the LoC.

The split is operational clarity, not new governance. The DAO is still the supreme authority over the protocol contracts.

## Rollout timeline

| Phase | What happens | Status |
| --- | --- | --- |
| Vote | AIP-5 passes Snapshot | Done (Apr 7, 2026) |
| Onchain deployments | New contracts (POL Fund, LoC tracker, govALB) deployed via team deployer | In progress (Apr–May 2026) |
| Cap raise execution | ALB token cap raised to 1.051 B via 14-day timelock | <!-- TODO:USER confirm execution date or pending date --> |
| Farming wind-down | Existing farms deprecated, replaced by Vaults / POL flows | In progress |
| esALB protection program | APR-stabilization for esALB holders during transition | <!-- TODO:USER confirm implementation status --> |
| Public dashboards | LoC drawdown tracker, POL holdings, buyback-and-burn cadence | <!-- TODO:USER planned launch --> |

The 18 unverified contracts deployed by the team deployer between April and May 2026 (visible on Basescan) are the AIP-5 rollout in flight.

## See also

- [AIP-5 — Building Alien Base 2.0](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — the full proposal.
- [Snapshot vote](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63)
- [ALB Token](alb-token.md)
- [Roadmap](roadmap.md)
- [Alien Foundation](alien-base-dao/alien-foundation.md) and [Alien Labs](alien-base-dao/alien-labs.md)
