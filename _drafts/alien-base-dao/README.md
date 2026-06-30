---
description: How Alien Base is governed
---

# Alien Base DAO

Alien Base is governed by the holders of $ALB through the Alien Base DAO. Decisions are made on Snapshot, executed by the [DAO Multisig](dao-multisig.md), and increasingly framed and stewarded by the [Alien Foundation](alien-foundation.md) and [Alien Labs](alien-labs.md) — see "How decisions move from idea to execution" below.

## Governance surfaces

| Layer | What it does | Where it lives |
| --- | --- | --- |
| **Snapshot space** | Off-chain weighted voting (esALB-weighted). Where every AIP and ADIP is voted on. | [`alienbase-dex.eth`](https://snapshot.org/#/alienbase-dex.eth) |
| **DAO Multisig** | 5-of-8 Gnosis Safe. Executes the on-chain actions implied by passed proposals. Holds the protocol treasury. | [`0x4ab9070b…71e5`](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5) |
| **Alien Foundation** | Cayman-registered, ownerless legal entity. Provides offchain legal footing for DAO operations. | See [Alien Foundation](alien-foundation.md) |
| **Alien Labs** | Offchain product/frontend/revenue arm introduced in [AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2). Builds the dApp and runs commercial operations. | See [Alien Labs](alien-labs.md) |
| **Discord forum + signal channels** | Public discussion, sentiment-checks, Q&A on draft proposals. | [Discord](https://discord.gg/alienbase) |

## Voting power

Voting power is weighted by **esALB** holdings (and selected esLP variants), not raw ALB. The full strategy is implemented as a fork of Snapshot's strategies engine — see [`alienbase-xyz/snapshot-strategies`](https://github.com/alienbase-xyz/snapshot-strategies) and the on-chain `EsVoting` helpers ([`0x3f8d116e…ddc1`](https://basescan.org/address/0x3f8d116e99bce42b38989a62394fa9bb532dddc1) and [`0xd3cfcb52…2e7b`](https://basescan.org/address/0xd3cfcb52ec5715652c5096bdf99ea078c4df2e7b)).

Under [AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2), a new **govALB** token will offer **10× voting power** in exchange for a ~2-year effective lock — designed to align voting weight with long-term commitment. Mechanics will be documented as it goes live.

## How decisions move from idea to execution

```
Idea / discussion           →  Discord, Medium drafts
       │
       ▼
Snapshot proposal (AIP/ADIP) →  alienbase-dex.eth space
       │  (3-day vote, esALB-weighted)
       ▼
Pass / fail
       │
       ├─ Pass → on-chain actions executed by DAO Multisig (or scheduled via timelock)
       └─ Pass → off-chain actions executed by Alien Labs / Foundation (operating-budget items)
```

## Proposal requirements

To submit a proposal, you need at least **100,000 ALB** of voting power (esALB-weighted) at the snapshot block.

A proposal must cover three sections:

- **Motivation** — why we're doing this, with data and analysis where relevant.
- **Description** — concrete plan of action, including the specific on-chain functions the DAO Multisig is expected to execute (changes to smart-contract parameters, ALB disbursement, or new contract deployments).
- **Result** — how the proposal achieves the goals, with potential drawbacks and mitigations.

Step-by-step for first-time proposers: [How to Propose](how-to-propose.md).

## What the DAO controls today

Per [AIP-2](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52) and subsequent proposals, the DAO Multisig holds privileged roles on:

- V2 Factory `feeToSetter`
- V3 Factory `owner`
- `UniversalDistributorController` (active farm controller, since June 2025) `owner`
- BunniHubController `owner`

Some contracts are **not yet** owned by the DAO Multisig — notably the Token Generator orchestrator, the EsProxyMaster, and the Area 51 Factory. The full surface and the migration plan is on the [Audits & Security](../audits-and-security.md#onchain-control-surface) page.

## Proposal history

A complete index with vote results: [AIP Index](aip-index.md).

Highlights:

- **AIP-1 (de facto, Aug 2023)** — emergency emission cut from 15 → 8 ALB/sec after sniper bots captured the initial liquidity.
- **AIP-2 (Nov 2023)** — V3 launch boost program; established the 50/40/10 fee split and the DAO Multisig.
- **AIP-3 (Oct 2024)** — second-halving DAO budget; raised DAO collection rate from 15% → 20%.
- **AIP-4 (Jun 2025)** — third-halving budget; community chose "prioritize DAO" path; authorized multi-year vesting.
- **ADIP-01 (Aug 2025)** — first proposal authored by "Alienbase Foundation (Proposed)"; six-month operating budget.
- **AIP-5 (Apr 2026)** — Alien Base 2.0: replaces farming with POL fund + buyback-and-burn; introduces govALB; raises supply cap to 1.051B.

Three smaller community-led proposals also passed in August 2025 (YouTube channel access, Academy pilot video, Academy thread channel).

## Treasury

The DAO Multisig holds the on-chain treasury. As of {{today}}:

- ETH: 0.032
- ALB: 5,963,076 (only the Safe's holding; the broader DAO-controlled treasury referenced in ADIP-01 is ~37M ALB distributed across multiple addresses)
- USDC: 6,993
- WETH: 2.74
- 174 other ERC-20 tokens (Bunni LPs, V2 LPs, partner tokens, memecoins received as fees or grants)

The treasury composition is updated continuously as fees are collected and budget is spent. Live views: [Basescan](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5) (asset balances), [Safe](https://app.safe.global/home?safe=base:0x4ab9070b7680f802cbf8322e597a4409902171e5) (pending Safe transactions), [Dune dashboard](https://dune.com/sealaunch/alienbase) (fee accrual over time).

## Discord & forum etiquette

Big proposals go through community discussion before they hit Snapshot. The norm is:

1. Post a draft / motivation in Discord (`#governance` or equivalent channel).
2. Iterate based on feedback for at least a few days.
3. Cross-post to Medium once the structure is settled (helps non-Discord users find it).
4. Open the Snapshot vote.

Spammy, bad-faith, or copy-paste proposals from non-engaged community members tend to die quickly. The DAO is small enough that signal-to-noise is high but also that any well-reasoned proposal gets a real read. Joining [Discord](https://discord.gg/alienbase) is by far the easiest way to be part of the conversation.
