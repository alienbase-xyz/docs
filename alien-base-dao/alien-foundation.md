---
description: The legal entity behind Alien Base
---

# Alien Foundation

The **Alien Foundation** is a Cayman-Islands-registered, ownerless legal entity established in **December 2024**. Its purpose is to give the Alien Base DAO a stable offchain legal footing — for partnerships, audits, fiat denominated services, and anything else that benefits from a real-world counterparty.

> _Last updated: July 6, 2026._

## Why it exists

DAOs are powerful coordination mechanisms but they cannot, by themselves, enter into contracts, hold a bank account, or be sued / sue. As Alien Base scaled past a single-multisig operation, it became practical to wrap the DAO's offchain activity in a legal shell that:

* Lets the DAO sign agreements with auditors, infrastructure providers, exchanges, and partners.
* Holds non-crypto assets (USDC operating reserves, fiat invoicing, etc.).
* Provides a defined liability boundary for contributors and the DAO itself.
* Can interact with regulators in jurisdictions that require a counterparty.

A Cayman foundation is the standard pattern for this in DeFi (Uniswap Foundation, Optimism Foundation, etc.). Cayman foundations can be **ownerless** — there is no shareholder, only beneficiaries (the DAO members) and supervisors. This means the Foundation cannot be captured by an external party.

## What it does

* Holds the operating-budget USDC reserves authorized by [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) and follow-up budget proposals.
* Engages auditors (currently Epsilon's audit; Mothership's audit is upcoming).
* Engages legal counsel for the DAO.

## What it does **not** do

* It does not control the DAO. Final say on every operating-budget decision still belongs to esALB voters.
* It does not own the protocol contracts. On-chain control surface is held by the DAO Multisig — see the [onchain control surface](../audits-and-security.md#onchain-control-surface).
* It is not the team. Operating contributors (development, design, marketing, ops) are paid by the Foundation under the budget the DAO approved, but they are not Foundation officers.

## Relationship to Alien Labs

[AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) introduced a clearer split:

* **Alien Base DAO** — onchain governance over protocol contracts. The supreme authority over the contracts.
* **Alien Foundation** — offchain legal entity, treasury custodian, counter-party for service contracts.
* **Alien Labs** — offchain product / frontend / revenue arm. Builds the dApp; runs commercial operations under the Foundation's umbrella.

See [Alien Labs](alien-labs.md) for detail on the Labs side.

## References

* [Alien Base 2025: Launching The Full Scale Invasion](https://medium.com/@alienbase/alien-base-2025-launching-the-full-scale-invasion-99d50163a5ed) — confirms Foundation established Dec 2024.
* [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) — first proposal authored as "Alienbase Foundation (Proposed)".
* [AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — formalizes the DAO / Foundation / Labs split.
