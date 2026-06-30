---
description: The DAO Multisig — signers, threshold, and policy
---

# DAO Multisig

The Alien Base DAO Multisig is the on-chain executor of every passed governance proposal that requires a contract action. It is also the protocol's primary treasury wallet.

> *Last updated: {{today}}.*

## At a glance

| | |
| --- | --- |
| Address | [`0x4ab9070b7680f802cbf8322e597a4409902171e5`](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5) |
| Type | Gnosis Safe (proxy via Safe Proxy Factory `0xC228…10BC`) |
| Threshold | **5 of 8** |
| Created | November 2023, following the passage of [AIP-2](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52) |
| Total executed Safe transactions | 28 (Blockscout counter; reflects on-chain actions executed by the Safe) |

Inspect the Safe in your browser via [app.safe.global](https://app.safe.global/home?safe=base:0x4ab9070b7680f802cbf8322e597a4409902171e5).

## Signers (8)

> The signer composition was last updated as part of AIP-2 implementation in late 2023. Confirmed via direct `eth_call` to `getOwners()` on the Safe.

The eight signer addresses are public:

1. `0x9da3587a5209fc6ffc4ffe0f0803bb16fe03b7eb`
2. `0x2360404108db5626fb326fadf1669c9b4911e704` — also the author of the August 2025 community proposals and ADIP-01
3. `0xa7ec7de675f35b51d59faaf48d1e2dacf9fb0bc9`
4. `0xd9c14e5ad86d06de762f0d179109661e5b60cc4d` — the original AIP-2 "DAO treasury wallet" EOA
5. `0xbf31124f7adacf777bb52109941e789808fc65f3`
6. `0xa209b82b3719d4dfc1928d24ca5ba4f1123985e6`
7. `0x9a4d392edea94ff73f0452ab482a0437eae9cad3`
8. `0x3f9bea132fcde4886e277c43e94c9dd08e0c1d82`

Per AIP-2 the multisig is structured to balance team and community signers. <!-- TODO:USER map each address to its human / role identifier (e.g., 0xAw, GotMyGat, etc.) — currently public docs only listed 6 signers and called it 4-of-6, which is now out of date -->

## What the multisig controls

Verified by direct `eth_call`:

| Contract | Privileged role |
| --- | --- |
| V2 Factory | `feeToSetter` |
| V3 Factory | `owner` |
| `UniversalDistributorController` (current farm controller) | `owner` |
| BunniHubController | `owner` |

Several contracts are **not yet** held by the DAO Multisig:

- Area 51 Factory `feeToSetter` — single-key EOA `0xa670…0166`
- Token Generator orchestrator `owner` — team deployer EOA `0xDD3705…0aD5`
- EsProxyMaster `owner` — team deployer EOA `0xDD3705…0aD5`
- Original `DistributorController` (legacy) — separate team operations Safe `0x845e2f13…f543`

Migrating these to the DAO Multisig is on the [Roadmap](../roadmap.md). The full surface is documented on the [Audits & Security](../audits-and-security.md#onchain-control-surface) page.

## Treasury balances

As of {{today}}:

- ETH: 0.032
- ALB: 5,963,076.89
- USDC: 6,993.51
- WETH: 2.74
- 174 additional ERC-20s (Bunni LPs, V2 LPs, partner tokens, memecoins received as fees or grants)

The Safe's ALB balance is the on-chain "DAO Multisig" share. The broader DAO-controlled ALB pool referenced in [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) (~37 M ALB) is distributed across multiple addresses including the team deployer and the original AIP-2 treasury EOA `0xD9c14E5A…cC4d`.

## Operating policy

- **Threshold of 5 of 8** ensures no single faction can act unilaterally.
- **Proposed actions** are typically queued in the Safe UI by one signer and signed off-chain by others over the days following a Snapshot vote.
- **Sensitive parameter changes** (e.g., emission-rate updates on the farm) are additionally subject to on-chain timelocks: 7 days on the `DistributorController` for emission changes, 14 days on ALB minting.
- **Treasury moves** (ALB transfers, USDC operating spend) are executed against the budget approved by the DAO via a passed AIP/ADIP.

## Open items

- <!-- TODO:USER -->Map each signer address to a public name / X handle / role (current docs only lists 6 signers; this is out of date).
- <!-- TODO:USER -->Document the signer rotation policy: how a signer is added or removed, and whether that requires a Snapshot vote.
- <!-- TODO:USER -->Disclose the OPSEC posture (e.g., are signers using hardware wallets exclusively? Geographic distribution? Backup signers?).
