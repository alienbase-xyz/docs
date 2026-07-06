---
description: Audit status and security posture of Alien Base contracts
---

# Audits & Security

This page tracks the security posture of every contract Alien Base has deployed. It is updated whenever a new audit report is published, a new contract is deployed, or a permission boundary changes.

> *Last updated: July 6, 2026.*

## Summary

Alien Base contracts fall into three buckets:

| Bucket | What it means | Examples |
| --- | --- | --- |
| **Audited** | Contracts written by Alien Base, audited by a third party, report complete. | Epsilon Router (+ off-chain meta-aggregator integration) |
| **Audit upcoming** | Contracts written by Alien Base that have an audit scoped and in flight, but no report yet. The contract may be live on mainnet behind supply caps or feature flags during this period. | Mothership |
| **Inherited upstream audits** | Forks of well-audited upstream protocols. Audit coverage applies only to the unchanged-core parts. | V2 / V3 core, BunniHub, SmartRouter, CarbonController, MasterChef-style farm |

We deliberately do not claim audit coverage we don't have. If you see a third-party article saying "Alien Base contracts have been audited by reputable firms" without naming the firm, date, scope, and report URL, treat it as marketing rather than evidence.

## Audited

### Epsilon Router — audited by Hexens

- **Auditor:** [Hexens](https://hexens.io/) — review led by Kasper Zwijsen, Head of Audits.
- **Scope:** the full Epsilon protocol — the on-chain Epsilon Router and Matcher (the contracts holding and settling all resting orders: Limit, Take Profit, Stop Loss, Trailing Stop, DCA), the TWAP / Redstone price-oracle layer, and the off-chain keeper + indexer infrastructure.
- **Contract:** [`0x303ca5c65AabCb1CE242DF93F478c41E0E4D2580`](https://basescan.org/address/0x303ca5c65AabCb1CE242DF93F478c41E0E4D2580) — verified source on Basescan.
- **Timeline:** audit started April 27, 2026; final report June 1, 2026 — before the July 2026 production launch.
- **Findings:** 37 total — 2 critical, 3 high, 14 medium, 12 low, 6 informational. Per the report: *"All reported issues were fixed or acknowledged by the development team and subsequently verified by us."*
- **Report:**

{% file src=".gitbook/assets/alienbase-epsilon-audit-hexens-2026.pdf" %}

- **What this means for users:** Epsilon is the path most swaps take, and the Router holds resting-order funds. Both critical issues (order registration without signature validation, keeper not bound into the signed order) were fixed and verified before any user funds touched the contract.

## Audit upcoming

### Mothership

- **Scope:** Alien Base's first ALM (Automated Liquidity Manager). Components include `MothershipVaultRouter`, `MothershipVaultPublic` (ERC-20 share vault), `UniManyDirectCore` (multi-range V3 position manager), and `UniManyDirectHelper`.
- **Status:** pre-audit hardening complete. The public [`Mothership`](https://github.com/alienbase-xyz/Mothership) repo includes an explicit `audit-scope` commit (Jan 15, 2026) and a fuzz-test suite. The audit firm and report will be published before the MVP is opened to the public without supply caps.
- **Pre-launch posture:** any Mothership contracts deployed before audit completion run with strict supply caps and gated access; see the [Vaults](liquidity/vaults.md) page for the live status.
- **Report:** *to be linked here when published.*

## Inherited upstream audits

For unchanged-core forks, the upstream auditor's findings transfer. We list what we forked, who originally audited it, and which Alien Base address it corresponds to.

### Uniswap V2 — V2 Factory, V2 Router, Area 51 Factory + Router, Pair contracts

- **Upstream auditors:** Uniswap V2 was audited by **dapp.org** (formerly New Alchemy) and ABDK (parts).
- **Reports:** [Uniswap V2 Audit Report — dapp.org](https://github.com/Uniswap/v2-core/blob/master/audits/dapphub/v2-audit-report.pdf), additional security reviews on [uniswap.org/audits](https://uniswap.org/audits).
- **Coverage on Alien Base:** the V2 Factory, V2 Router, and the equivalent Area 51 Factory + Router are stock Uniswap V2 with no modifications to the audited core paths.

### Uniswap V3 — V3 Factory, NFTPositionManager, V3 Pools

- **Upstream auditors:** **Trail of Bits**, **ABDK**, plus the **Uniswap V3 Code4rena** contest (2021).
- **Reports:** [uniswap.org/audits](https://uniswap.org/audits).
- **Coverage on Alien Base:** the V3 Factory, NFTPositionManager, multicall, TickLens, and NFT renderer are stock Uniswap V3.

### PancakeSwap MasterChef — `BasedDistributorV2` farm

- **Upstream auditors:** PancakeSwap MasterChef (and MasterChefV2) audits by **PeckShield** and **CertiK**.
- **Reports:** linked from the PancakeSwap docs.
- **Coverage on Alien Base:** the `BasedDistributorV2` contract, the `DistributorController` family, the new `UniversalDistributorController` (active since June 5, 2025), and the dual-reward `ComplexRewarderPerSecV4` contracts use the MasterChef pattern.

### PancakeSwap SmartRouter — V3 SmartRouter

- **Upstream auditor:** **CertiK**.
- **Reports:** linked from the PancakeSwap docs.
- **Coverage on Alien Base:** the SmartRouter at `0xB20C411F…9411` is forked from PancakeSwap and **lightly adapted**. Adaptations (notably native-Carbon support and Alien-Base-specific routing) are not covered by the upstream report and fall under the Epsilon audit scope.

### Bunni / Timeless Finance — BunniHub, BunniZap, BunniToken

- **Upstream auditors:** Bunni V1 audited by Spearbit (commissioned by Timeless Finance).
- **Reports:** see [Bunni docs](https://docs.bunni.pro/).
- **Coverage on Alien Base:** the BunniHub at `0xDC53487e…aC6F`, BunniZap at `0x6947DA28…D75D`, and BunniLensV2 are upstream Bunni. **BunniZap is lightly adapted for Alien Base** — adaptations are not covered by the upstream report.

### Bancor Carbon — CarbonController + Voucher

- **Upstream auditors:** **PeckShield** (Carbon v1.0 — May 29, 2024; CarbonVortex v1.0.1 — July 31, 2024); **ChainSecurity** (Carbon, undated in upstream README).
- **Reports** (mirrored in our fork's `docs/audits/`):
  - [PeckShield — Carbon v1.0](https://github.com/alienbase-xyz/carbon-contracts/blob/dev/docs/audits/PeckShield-Audit-Report-Bancor-Carbon-v1.0.pdf)
  - [PeckShield — CarbonVortex v1.0.1](https://github.com/alienbase-xyz/carbon-contracts/blob/dev/docs/audits/PeckShield-Audit-Report-Bancor-CarbonVortex-v1.0.1.pdf)
  - [ChainSecurity — Carbon](https://github.com/alienbase-xyz/carbon-contracts/blob/dev/docs/audits/ChainSecurity_Carbon_Audit_Report.pdf)
- **Coverage on Alien Base:** the CarbonController at `0xe3763886…716e` (deployed Aug 12, 2024) and the Voucher proxy at `0x2f3b0d35…2dc9` ("CARBON-STRAT" NFT) are the unchanged Bancor implementation. Alien Base did not modify these contracts. Carbon order creation is [deprecated](archive/carbon-orders.md) as of July 2026, but the contracts remain live and existing orders stay withdrawable.

### Camelot xGRAIL — esALB / EsToken family

- **Upstream pattern:** The escrow / lock model derives from Camelot's xGRAIL system.
- **Coverage on Alien Base:** the EsToken contracts (`0xe1afc637…4587` and others), EsProxyMaster (`0xd3968a4a…ec88`), EsTokenController (`0x154d41a9…ea99`), EsVoting helpers, and esLP wrappers are Alien-Base-implemented based on the xGRAIL pattern. They are not separately audited; we treat them as "inherited pattern" rather than "inherited audit". A dedicated audit may be commissioned as part of the AIP-5 / 2.0 rollout.

## Onchain control surface

A security review is incomplete without checking *who* can pull which lever. As of July 6, 2026:

| Contract | Privileged role | Holder | Type |
| --- | --- | --- | --- |
| ALB token | DEFAULT_ADMIN_ROLE (OZ AccessControl) | Team Safe / DAO | Multisig |
| V2 Factory | `feeToSetter` | DAO Safe `0x4ab9070b…71e5` | 5-of-8 Gnosis Safe |
| V3 Factory | `owner` | DAO Safe | 5-of-8 Gnosis Safe |
| `UniversalDistributorController` (current farm controller, active since 2025-06-05) | `owner` | DAO Safe | 5-of-8 Gnosis Safe |
| Original `DistributorController` (legacy) | `owner` | Team operations Safe `0x845e2f13…f543` | Separate Safe (legacy) |
| Area 51 Factory | `feeToSetter` | EOA `0xa670…0166` | Single key — *gap* |
| Token Generator orchestrator | `owner` | Team deployer EOA `0xDD3705…0aD5` | Single key — *gap* |
| EsProxyMaster | `owner` | Team deployer EOA | Single key — *gap* |

The "gaps" above are contracts whose privileged owner is still a team-controlled EOA rather than the DAO Multisig. These are surface area we plan to migrate to the DAO Safe; the migration is tracked in the [Roadmap](roadmap.md) and any change will be announced via Snapshot proposal.

## Multisig & timelock

- **DAO Multisig**: [`0x4ab9070b7680f802cbf8322e597a4409902171e5`](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5) — 5-of-8 Gnosis Safe. Signers and policy: see [DAO Multisig](alien-base-dao/dao-multisig.md).
- **Timelock**: an OpenZeppelin `TimelockController` is deployed at [`0x1c7e4284…1e21`](https://basescan.org/address/0x1c7e4284423c1a2362c49b1ea223b73e38c81e21). The original `DistributorController` enforces a 7-day delay on emission-rate changes; ALB token mint changes go through a 14-day total time lock.

## Bug bounty

The DAO budget (per ADIP-01) includes a line item for "audits, bug bounties, hosting, nodes, and third-party development". A formal bug-bounty program with explicit severity tiers and contact channels is **on our list to formalize** but not yet live. In the meantime, please report security issues directly to the team via Discord (DM a team member) or email **dex@alienbase.xyz**.

## What to verify yourself

For any contract you interact with:

1. Open the Basescan link from [Contracts](contracts.md). Confirm the **"Contract"** tab is green ("Contract Source Code Verified").
2. Read the contract's deployer + creation tx. The vast majority of Alien Base contracts were deployed by [`0xDD3705A1c50Fc84B6d31394aA8F4D568B98a8AD5`](https://basescan.org/address/0xDD3705A1c50Fc84B6d31394aA8F4D568B98a8AD5) (publicly tagged "AlienBase: Deployer" on Basescan).
3. For owned contracts, call `owner()` from Basescan's Read tab to confirm who controls them.
4. For Safe-owned contracts, you can independently inspect the Safe at [app.safe.global/base:0x4ab9070b…71e5](https://app.safe.global/home?safe=base:0x4ab9070b7680f802cbf8322e597a4409902171e5).

## Reporting a vulnerability

Don't post a 0-day in public. Reach the team privately first:

- DM the team via [Discord](https://discord.gg/alienbase) — find a moderator with a "Team" or "Core" role.
- Email **dex@alienbase.xyz**.
- After the issue is patched and disclosed, we publish a postmortem on [Medium](https://medium.com/@alienbase) and link it from the [Changelog](changelog.md).
