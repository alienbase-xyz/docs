---
description: How protocol fees are distributed to esALB stakers as WETH yield
---

# Real Yield (WETH)

**Real Yield** is the share of Alien Base's protocol fees that is paid out to esALB stakers in **WETH** (and other liquid assets), rather than as additional ALB inflation.

It's the central reason esALB exists: instead of diluting holders with emissions, the protocol returns a portion of its actual revenue to the people who lock long-term.

> *Last updated: July 6, 2026.*

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

- **V2 pools.** Pools charge **0.16%** per swap, paid to LPs in-pool. The V2 Factory's `feeToSetter` is the DAO Multisig — the protocol-side carve-out can be enabled by DAO vote.
- **V3 pools.** Each fee tier collects fees automatically; **50% goes to LPs and 50% goes to esALB stakers** as Real Yield. The seven tiers are 0.01% / 0.02% / 0.03% / 0.04% / 0.075% / 0.30% / 1.00%. (AIP-2 originated the LP/staker fee-sharing structure; the current split is 50/50.)
- **Epsilon platform fees** on every swap — **0.01%** stables / **0.05%** blue chips / **0.15%** everything else, plus the flat 0.05% Matcher execution fee. Routed to the Treasury / esALB stream.
- **Epsilon Router orders** — tiered fees on Limit / Take Profit (0.01–0.10%), Stop Loss / Trailing Stop (0.10–0.45%), and DCA chunks (0.01–0.20%), each plus the 0.05% Matcher fee. Routed to the Treasury / esALB stream. Full table: [Fees](../fees.md).

The protocol share is converted into **WETH** (and select stablecoins / partner tokens) and distributed pro-rata to esALB stakers via the EsToken reward distributor (`EsTokenController` and the rewarder family — see [Contracts](../contracts.md)).

## What you receive

When you stake esALB in the esALB Single Stake vault:

- **Unlocked ALB rewards** — the standard farm-style emissions stream.
- **Real Yield** — primarily WETH; some weeks may include USDC, ETH, or tokens received as fees.

Both streams are claimable from the same Vaults page UI ("Harvest" / "Claim All").

## Historical context

- Pre-esALB (Aug 2023 → Apr 2024): protocol fees accrued to the team / DAO; no direct user-share mechanism.
- esALB launch (Apr 2024) introduced single-staking with ALB rewards.
- AIP-2 (Nov 2023) established the V3 LP / staker fee-sharing structure that powers Real Yield today (originally 60/40, since normalized to 50/50).
- AIP-3 (Oct 2024) noted that ~50% of trade-fee revenue was already being redistributed to esALB holders by that point.
- AIP-5 (Apr 2026) preserves Real Yield and adds the POL Fund's buyback-and-burn flywheel on top.

## Open items

- <!-- TODO:USER -->Concrete numbers: most recent month/quarter Real Yield distribution in WETH (and any other tokens), plus implied APR vs. the staked esALB pool size. The Dune dashboard's **Fees** widget shows protocol-fee accrual; we should be able to derive recent Real Yield from it: [dune.com/sealaunch/alienbase](https://dune.com/sealaunch/alienbase).
- <!-- TODO:USER -->Distribution cadence — is Real Yield streamed continuously or distributed in epochs? Which contract / function is the user-facing "claim"?
- <!-- TODO:USER -->Explain how the protocol handles long-tail fee tokens (e.g., a memecoin pool that produces fees in the memecoin) — are they auto-swapped to WETH, distributed in-kind, or kept by the DAO?

## See also

- [esALB](README.md)
- [Fees](../fees.md) — full fee schedule and where each fee goes.
- [ALB Token — Value flow](../alb-token.md#value-flow-real-yield)
