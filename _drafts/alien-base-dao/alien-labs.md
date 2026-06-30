---
description: The product/build arm of Alien Base
---

# Alien Labs

**Alien Labs** is the offchain product, frontend, and revenue arm of Alien Base, formalized in [AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) (April 2026).

> *Last updated: {{today}}.*

## What it is

Alien Labs is the entity that:

- Designs and builds the [app.alienbase.xyz](https://app.alienbase.xyz) frontend.
- Develops new on-chain products before they're handed off to the DAO (Mothership, Epsilon Router, Token Generator v2, etc.).
- Runs the commercial side of Alien Base — partnerships, integrations, listings, market making.
- Operates day-to-day infrastructure (RPC, indexers, frontends, analytics).

It operates under the [Alien Foundation](alien-foundation.md)'s legal umbrella but is structured as a distinct working unit so that builders, designers, and operators have clear contracts, deliverables, and accountability.

## How it's funded

Through a **Dev Line of Credit (LoC)** introduced in AIP-5. Mechanics:

- The LoC replaces the older "X ALB/month dev allowance" flat budget.
- Funding is treated as **tracked debt** with interest paid to esALB holders. Every ALB drawn from the LoC increases an outstanding-debt balance the Foundation owes back to the protocol.
- **Price-tier grants:** when ALB sustains a moving-average price of $0.40, $1, or $2, a tranche of the outstanding LoC unlocks as a grant — the debt at that tier is cleared. This aligns Labs's funding with the protocol's economic success.
- **esALB inflation coverage:** while the LoC is active, esALB holders receive a continuous APR designed to backstop dilution. Projected esALB yield from this mechanism: **30–35%** at expected operating volumes.

The full design is in the [AIP-5 proposal](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2).

## Why split DAO / Labs?

Three reasons:

1. **Cleaner accountability.** Builders sign normal employment / contractor agreements. The DAO holds the contracts and treasury; Labs holds the deliverables. If a build fails, the DAO can re-direct work without protocol-level disruption.
2. **Cleaner economics.** The DAO's incentive is protocol value (esALB yield, ALB price). Labs's incentive is delivery, with payouts tied to that value. The LoC mechanism makes the alignment formal.
3. **Cleaner governance.** Tokenomics decisions stay with the DAO. Product decisions stay with Labs (within the budget the DAO approved). This avoids the "every UI tweak goes to a Snapshot vote" failure mode.

## How Labs reports back

- **Quarterly Medium retrospectives** on what shipped vs. what was planned.
- **Monthly Discord updates** in the announcements channel.
- **Six-month operating-budget proposals** — the next ADIP-style budget after [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) is the cadence.
- **The Public [Changelog](../changelog.md)** is updated continuously as features ship.

## Open items

- <!-- TODO:USER -->Headcount + roles, even at a high level (e.g., "8 full-time + N contributors" with rough breakdown by function).
- <!-- TODO:USER -->Hiring channels / how to apply.
- <!-- TODO:USER -->Public reporting cadence — confirm quarterly retrospectives.
- <!-- TODO:USER -->LoC drawdown tracker — once the system is live, link to a public dashboard / spreadsheet showing current outstanding LoC balance and tier progress.
