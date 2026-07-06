---
description: Alien Base's automated liquidity manager — the next-gen Vault layer
---

# Mothership (pre-launch)

**Mothership** is Alien Base's purpose-built **Automated Liquidity Manager (ALM)**. It's the first protocol Alien Base has written from scratch (no upstream fork). Mothership turns passive concentrated-liquidity Vaults into actively managed strategies that re-balance ranges and re-allocate capital on the fly.

> _Last updated: July 6, 2026._ Mothership is **pre-launch** as of the time of writing — audit in flight, alpha imminent. Everything below describes the design; details may shift before launch.

## What Mothership is

A modular ALM with a **strategy-plugin architecture**. Each plugin is a smart contract that implements a defined set of tools (e.g., "manage multiple V3 Positions in a single vault"). Mothership routes user deposits into the strategy of their choice, and the strategy actively manages the underlying V3 NFT(s) on the user's behalf.

Concretely:

* **Multi-range positions.** A single Mothership strategy can hold multiple V3 ranges simultaneously, with arbitrary weights.
* **Auto-rebalance.** The strategist defines the rebalancing logic. Users do not need to touch anything.
* **Signal-driven.** Strategies can use volatility data, time-of-day patterns, or external signals to allocate capital.
* **Composable.** Mothership shares are ERC-20 — fully composable in DeFi.

## How it differs from Bunni Vaults

|                 | Bunni Vault                                 | Mothership Vault                                            |
| --------------- | ------------------------------------------- | ----------------------------------------------------------- |
| Range           | Fixed at deploy time                        | Dynamic per strategy                                        |
| Rebalance       | User migrates manually when bounds drift    | Strategy rebalances automatically                           |
| Granularity     | Single range, single fee tier               | Multi-range, multi-tier possible                            |
| Strategy author | Protocol (range definition)                 | Anyone (in the future marketplace)                          |
| Best for        | LPs who want predictable bounds and low gas | LPs who want max-yield + are willing to delegate management |

Both will coexist on the [Vaults](vaults.md) page once Mothership ships. They're not competing; they serve different LP profiles.

## Public alpha — what to expect

The first public release will run with **strict supply caps** until the audit completes its formal review and the team is comfortable expanding capacity:

* A small number of curated strategies, single-pair to start.
* Capped per-Vault TVL.
* Conservative range parameters.
* Active monitoring; emergency-pause readiness.

The caps are not a permanent feature — they're a launch-safety mechanism. They'll lift as the team gains operational confidence and the audit closes.

## The marketplace vision

Mothership's strategy-plugin design is intentional. The end-state is a **marketplace of liquidity managers**:

* Third-party strategists publish their own strategies (separate contracts implementing the Mothership interface).
* Users browse, compare historical performance, and allocate capital to strategies they trust.
* Strategists earn fees on the assets under management.
* The protocol takes a small slice of those fees as Real Yield to esALB.

This is a long-term roadmap item — see [Roadmap](../roadmap.md). The MVP is single-strategy, team-published. The marketplace turns on after the protocol matures.

## Audit status

**Audit in flight.** Pre-audit hardening is visible in the public Mothership repo: extensive fuzz tests and an `audit-scope` commit dated January 2026 marking the contracts the auditor is reviewing. The audit will complete before the MVP is publicly accessible without supply caps. Full audit framing: [Audits & Security](../audits-and-security.md).

## See also

* [Vaults overview](vaults.md)
* [Concentrated Liquidity (V3)](v3.md)
* [Bunni explainer](bunni.md) — Mothership builds on the same V3 substrate, but adds active management.
* [Roadmap](../roadmap.md)
* [Audits & Security](../audits-and-security.md)
