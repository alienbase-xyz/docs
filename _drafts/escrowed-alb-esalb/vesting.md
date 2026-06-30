---
description: Long-form ALB vesting via the VestingFactory contract
---

# Vesting

Some ALB allocations — to the team, contributors, advisors, and certain DAO-budgeted recipients — are released over multi-year schedules through the on-chain **VestingFactory** instead of via direct distribution.

> *Last updated: {{today}}.*

## What it is

`VestingFactory` is a contract deployed by the team in **June 2025** that creates per-recipient vesting contracts. Each per-recipient vesting contract holds an ALB allocation and releases it linearly over a configurable schedule.

This is distinct from the **esALB** locking system:

- **esALB** is short-term, holder-controlled, instantly mintable from ALB, and unlocks in 30 days or 1%/12h.
- **Vesting** is long-term, multi-year, and release schedules are fixed by the proposal that authorized them. The recipient cannot accelerate redemption.

The combination of the two ensures that long-tail contributor allocations reach circulating supply slowly while short-term holder behavior remains liquid via the esALB unlock paths.

## Origin

The team-facing 5 M ALB from the original timelock (see [ALB Token — Initial supply & distribution](../alb-token.md#initial-supply--distribution)) was always intended to vest. At launch, the vesting infrastructure had not yet been built — the original docs noted "team vesting was yet to be deployed". `VestingFactory` is that deployed infrastructure.

[AIP-3](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd) (Oct 2024) and [AIP-4](https://snapshot.org/#/alienbase-dex.eth/proposal/0x3e1f7e1841389638f6fda99baefd61331cf711fdc7f4649ad96713c25a747826) (Jun 2025) both authorized additional vested allocations:

- AIP-3 transferred 66% of the previous dev-team emissions rights into vested positions for DAO contributors, devs, and potential external investors.
- AIP-4 authorized esALB-style multi-year additional locks vesting over close to 5 years total since launch.

## Which addresses receive vesting

Vesting recipients include (non-exhaustive):

- Founding team members (the original 5 M ALB allocation).
- Long-term core developers and operators.
- Recipients of the AIP-3 / AIP-4 vested allocations.

The full list of recipient addresses is on-chain — every per-recipient vesting contract is created by `VestingFactory` and is therefore visible on Basescan via the factory's contract-creation history. <!-- TODO:USER provide the VestingFactory address so we can link the explorer view directly -->

## How it interacts with circulating supply

ALB held in vesting contracts is **non-circulating** until released. The "circulating supply" figure on CoinGecko / DefiLlama / DexScreener excludes:

- Tokens still in vesting contracts (not yet released to the recipient).
- Tokens locked as esALB (locked, but technically held by the user — counted as circulating in some methodologies).

Per the latest analytics, ~234 M ALB is reported as circulating against ~461 M minted. The gap is split between vesting contracts, the DAO multisig & treasury addresses, the team operations Safe, and unvested farm-emission accumulator state.

## See also

- [ALB Token — Initial supply & distribution](../alb-token.md#initial-supply--distribution)
- [AIP-3](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd) and [AIP-4](https://snapshot.org/#/alienbase-dex.eth/proposal/0x3e1f7e1841389638f6fda99baefd61331cf711fdc7f4649ad96713c25a747826)
- [Contracts — Vesting](../contracts.md) for `VestingFactory` address and per-recipient instances.
