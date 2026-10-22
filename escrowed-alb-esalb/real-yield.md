---
description: How protocol fees are distributed to esALB stakers as WETH yield
---

# Real Yield (WETH)

**Real Yield** is the share of Alien Base's protocol fees that is paid out to esALB stakers in **WETH** (and other liquid assets), rather than as additional ALB inflation.

It's the central reason esALB exists: instead of diluting holders with emissions, the protocol returns a portion of its actual revenue to the people who lock long-term.

> _Last updated: October 22, 2026._ With Alien Base 2.0, Real Yield is paid to holders of the **new** esALB and govALB. Old esALB holders should [migrate](../migration/README.md).

## How it works

```
   Trade on Alien Base (V2 / V3 / Carbon / DCA)
                 │
                 ▼
        Pool fees (LP share + protocol share)
                 │
        ┌────────┴────────┐
        ▼                 ▼
       LPs          Protocol share
                          │
                          ▼
              ┌───────────┴────────────┐
              ▼                ▼       ▼
       esALB stakers       DAO     POL Fund
       (Real Yield in     treasury (per AIP-5)
       WETH + tokens)
```

Protocol-share collection mechanics:

* **V2 pools.** Pools charge **0.16%** per swap, paid to LPs in-pool. The V2 Factory's `feeToSetter` is the DAO Multisig — the protocol-side carve-out can be enabled by DAO vote.
* **V3 pools.** Each fee tier collects fees automatically; **50% goes to LPs and 50% goes to esALB stakers** as Real Yield. The seven tiers are 0.01% / 0.02% / 0.03% / 0.04% / 0.075% / 0.30% / 1.00%. (AIP-2 originated the LP/staker fee-sharing structure; the current split is 50/50.)
* **Epsilon platform fees** on every swap — **0.01%** stables / **0.05%** blue chips / **0.15%** everything else, plus the flat 0.05% Matcher execution fee. Routed to the Treasury / esALB stream.
* **Epsilon Router orders** — The 0.05% Protocol fee is routed to the esALB real yield stream. Full table: [Fees](../fees.md).

The protocol share is converted into **WETH** (and select stablecoins / partner tokens) and distributed pro-rata to esALB and govALB holders through the Alien Base 2.0 **staking contract** ([`0x28a3…85cf`](https://basescan.org/address/0x28a3c9852383eef436a874b74d2acf23047e85cf)). Before the migration this ran through the legacy `EsTokenController` and rewarder family (see [Contracts](../contracts.md)).

## What you receive

When you hold new esALB or govALB (no staking step needed):

* **ALB rewards** — including the ALB left behind by holders who exit esALB early.
* **Real Yield** — primarily WETH; some weeks may include other tokens received as fees.

Rewards are shared per token: 1 esALB and 1 govALB earn the same. Claim them from the app, or call `claim` on the staking contract with the reward tokens you want.

_Legacy esALB_ earned these streams only while staked in the esALB Single Stake vault, and they were claimed with "Harvest" / "Claim All" on the Vaults page.

## Historical context

* Pre-esALB (Aug 2023 → Apr 2024): protocol fees accrued to the team / DAO; no direct user-share mechanism.
* esALB launch (Apr 2024) introduced single-staking with ALB rewards.
* AIP-2 (Nov 2023) established the V3 LP / staker fee-sharing structure that powers Real Yield today.
* AIP-3 (Oct 2024) noted that \~50% of trade-fee revenue was already being redistributed to esALB holders by that point.
* AIP-5 (Apr 2026) preserves Real Yield and adds the POL Fund's buyback-and-burn flywheel on top.
* Alien Base 2.0 migration (Oct 2026): Real Yield moves to the new staking contract and is paid automatically to new esALB and govALB holders.

## See also

* [esALB](./)
* [Fees](../fees.md) — full fee schedule and where each fee goes.
* [ALB Token — Value flow](../alb-token.md#value-flow-real-yield)
