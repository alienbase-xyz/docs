---
description: Canonical list of every Alien Base contract on Base
---

# Contracts

Every contract Alien Base has deployed on Base (chain id 8453). Each row links to Basescan and notes who controls it. Verification status, source repos, and audit coverage are tracked separately on the [Audits & Security](audits-and-security.md) page.

> *Last updated: {{today}}.*
> *Verification was performed against [Blockscout](https://base.blockscout.com/) and confirmed via `eth_call` on the public Base RPC.*

## How to read this page

- **Active** = the canonical address users and integrators should reference today.
- **Superseded** = an earlier deployment that has been replaced. Listed for transparency; do not interact.
- **Deprecated** = a product line that is no longer maintained. Listed for historical reference only — see [Archive](archive/README.md) for context.
- A row marked with `(DAO)` means the contract's owner / fee setter is the [DAO Multisig](alien-base-dao/dao-multisig.md). Rows marked `(team)` mean the role is still held by a team-controlled key — see the [Audits & Security](audits-and-security.md) page for our migration plan.

## Token

| | |
| --- | --- |
| **ALB token** | [`0x1dd2d631c92b1aCdFCDd51A0F7145A50130050C4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) |
| Standard | ERC-20, 18 decimals, OpenZeppelin AccessControl |
| Max supply (current) | 510,000,000 ALB ([AIP-5](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63) authorizes a one-time raise to 1,051,000,000) |
| Mint timelock | 14 days |

## Alien Base V2

The original AMM. Stock Uniswap V2 plus a PancakeSwap-style farming layer.

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| V2 Factory | [`0x3e84d913803b02a4a7f027165e8ca42c14c0fde7`](https://basescan.org/address/0x3e84d913803b02a4a7f027165e8ca42c14c0fde7) | Active | `feeToSetter` = DAO Multisig (DAO) |
| V2 Router | [`0x8c1A3cF8f83074169FE5D7aD50B978e1cD6b37c7`](https://basescan.org/address/0x8c1A3cF8f83074169FE5D7aD50B978e1cD6b37c7) | Active | (immutable) |
| V2 Zap helper | [`0xe0808b8e2bdd70d70e540f977cf40e26e5811054`](https://basescan.org/address/0xe0808b8e2bdd70d70e540f977cf40e26e5811054) | Active | (helper) |
| V2 Router (legacy) | `0x3bd2…2224`, `0x7f2f…786e`, `0xfb86…94a0` | Superseded | Do not use — replaced 2023-08-25 |

## Farming (MasterChef-style)

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| Farm — `BasedDistributorV2` | [`0x52eaecac2402633d98b95213d0b473e069d86590`](https://basescan.org/address/0x52eaecac2402633d98b95213d0b473e069d86590) | Active | Controller below |
| **UniversalDistributorController** (current controller, since 2025-06-05) | [`0x62d58b4cdd96b590ff4174e272b5f41693c8fba9`](https://basescan.org/address/0x62d58b4cdd96b590ff4174e272b5f41693c8fba9) | **Active** | DAO Multisig (DAO) |
| `DistributorController` (original) | [`0x16f1F80654F2FEA97293321675907CFA2e23e4fB`](https://basescan.org/address/0x16f1F80654F2FEA97293321675907CFA2e23e4fB) | Superseded | Team operations Safe `0x845e2f13…f543` |
| OpenZeppelin `TimelockController` | [`0x1c7e4284423c1a2362c49b1ea223b73e38c81e21`](https://basescan.org/address/0x1c7e4284423c1a2362c49b1ea223b73e38c81e21) | Active | (governance helper) |
| `ComplexRewarderPerSecV4` (dual rewards) | multiple addresses, deployed 2023-08 → 2024-12 | Active | per-farm |

> **Note on the docs migration:** The previous version of this page labelled `0x16f1F806…e4fB` as the "Farm Timelock Proxy". It is the **original** `DistributorController` itself — a thin contract that enforces a 7-day delay on emission changes — and as of 2025-06-05 it is no longer the active farm controller (replaced by `UniversalDistributorController`). The OZ-style `TimelockController` is a separate contract listed above.

## Alien Base V3 (Concentrated Liquidity + Bunni)

Stock Uniswap V3 plus a fork of Bunni for ERC-20-wrapped LP positions.

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| V3 Factory | [`0x0Fd83557b2be93617c9C1C1B6fd549401C74558C`](https://basescan.org/address/0x0Fd83557b2be93617c9C1C1B6fd549401C74558C) | Active | DAO Multisig (DAO) |
| V3 NFTPositionManager (`ALB-V3-POS`) | [`0xB7996D1ECD07fB227e8DcA8CD5214bDfb04534E5`](https://basescan.org/address/0xB7996D1ECD07fB227e8DcA8CD5214bDfb04534E5) | Active | — |
| V3 SmartRouter (V2+V3 unified) | [`0xB20C411FC84FBB27e78608C24d0056D974ea9411`](https://basescan.org/address/0xB20C411FC84FBB27e78608C24d0056D974ea9411) | Active | (immutable) |
| QuoterV2 | [`0x353b1bea…b23a`](https://basescan.org/address/0x353b1bea3a9b1a9b6e2a9c7e6e4a4d4d4d4d4d4d) | Active | — |
| MixedRouteQuoterV1 | [`0xa54844d4…fde6`](https://basescan.org/address/0xa54844d4) | Active | — |
| TickLens | [`0xe3b6a547…fbd8e`](https://basescan.org/address/0xe3b6a547) | Active | — |
| Multicall | [`0x24fff20e…32fe`](https://basescan.org/address/0x24fff20e) | Active | — |
| **BunniHub** (active) | [`0xd1fac4f51457e4a6d35bdc7311718e5d6de92bb9`](https://basescan.org/address/0xd1fac4f51457e4a6d35bdc7311718e5d6de92bb9) | **Active** | — |
| BunniHub (original) | [`0xDC53487e2a6eF468260Bc938F645f84caaccAC6F`](https://basescan.org/address/0xDC53487e2a6eF468260Bc938F645f84caaccAC6F) | Superseded by BunniHubA (2024-08-09) | — |
| BunniHubController | [`0x4bcc584979817219585b6a62a5bb6c15c1fa0f38`](https://basescan.org/address/0x4bcc584979817219585b6a62a5bb6c15c1fa0f38) | Active | DAO Multisig (DAO) |
| **BunniZap** (active) | [`0x77c18d8aea11147b65d9e3ee7b3a9e89910ab7f0`](https://basescan.org/address/0x77c18d8aea11147b65d9e3ee7b3a9e89910ab7f0) | **Active** | — |
| BunniZap (original) | [`0x6947DA282E447a2e9d65ff00aAf80efB5116D75d`](https://basescan.org/address/0x6947DA282E447a2e9d65ff00aAf80efB5116D75d) | Superseded (2024-09-02) | — |
| BunniLensV2 | latest at [`0x1733c304…9c44`](https://basescan.org/address/0x1733c304) | Active | — |
| Sample BunniToken (LP) | varies per pool — see the Vaults page in the app | — | — |

> **Note on the docs migration:** the previous version of this page listed `0x176ca19…08f0` as the "esALB-ETH pair". That contract is a `BunniToken` (a wrapped V3 LP position over the ALB/WETH pool), **not** a Uniswap V2 pair. Bunni LP tokens are minted by BunniHub, not by the team deployer.

## esALB & escrowed token system

The escrow / lock system follows Camelot's xGRAIL pattern.

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| esALB (`EsToken`, name "Escrowed ALB", symbol `esALB`) | [`0xe1afc637f41e05efe08d55296a2ccff0072a4587`](https://basescan.org/address/0xe1afc637f41e05efe08d55296a2ccff0072a4587) | Active | — |
| esALB (alt — referenced in the historical "Changing allowance" guide) | [`0x365c6d588e8611125De3bEA5B9280C304FA54113`](https://basescan.org/address/0x365c6d588e8611125De3bEA5B9280C304FA54113) | Co-deployed 2024-04-25 — see [Changing allowance](escrowed-alb-esalb/changing-allowance.md) | — |
| `EsProxyMaster` (esALB system orchestrator) | [`0xd3968a4a07d64c6e16982d45191b9a09a261ec88`](https://basescan.org/address/0xd3968a4a07d64c6e16982d45191b9a09a261ec88) | Active | Team deployer (team) |
| `EsTokenController` (refresh, 2025-06-05) | [`0x154d41a96ad37570a2ad6849063d0b480da1ea99`](https://basescan.org/address/0x154d41a96ad37570a2ad6849063d0b480da1ea99) | Active | — |
| `esLP-ALB-ETH` (escrowed LP) | [`0x3d3a5ad6d7beab234d7f0338a01e62b1d36d8ea0`](https://basescan.org/address/0x3d3a5ad6d7beab234d7f0338a01e62b1d36d8ea0) | Active | — |
| `esLP-B-ALB-ETH` ("Backstop") | [`0x4a023efe4b5cd304e800f29074186164fda36978`](https://basescan.org/address/0x4a023efe4b5cd304e800f29074186164fda36978) | Active | — |
| `EsVoting` (governance weight helpers) | [`0x3f8d116e99bce42b38989a62394fa9bb532dddc1`](https://basescan.org/address/0x3f8d116e99bce42b38989a62394fa9bb532dddc1), [`0xd3cfcb52ec5715652c5096bdf99ea078c4df2e7b`](https://basescan.org/address/0xd3cfcb52ec5715652c5096bdf99ea078c4df2e7b) | Active | — |
| `EsComplexRewarder` (dual rewards for escrowed LPs) | multiple, see the Farms page | Active | — |

## Vesting

Multi-year vesting for team and DAO contributors authorized by [AIP-4](https://snapshot.org/#/alienbase-dex.eth/proposal/0x3e1f7e1841389638f6fda99baefd61331cf711fdc7f4649ad96713c25a747826).

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| `VestingFactory` | [`0x77ec0394e4edea1997bdb1919bb354d880faed84`](https://basescan.org/address/0x77ec0394e4edea1997bdb1919bb354d880faed84), [`0xf61cc1aedd072784d8f133ba9409c538cfc9453d`](https://basescan.org/address/0xf61cc1aedd072784d8f133ba9409c538cfc9453d) | Active | — |
| `TokenLock` (legacy launch-time team lock) | [`0x329efd9209f1ae6f43568b85e9bdf69105fb8b0c`](https://basescan.org/address/0x329efd9209f1ae6f43568b85e9bdf69105fb8b0c) | Historical | — |

## Carbon (Limit / Range / Recurring orders)

A direct integration of Bancor's Carbon protocol — Alien Base was the first DEX to integrate Carbon natively rather than via a license.

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| `CarbonController` | [`0xe3763886bf91d5466b416b37fdf2b6337897716e`](https://basescan.org/address/0xe3763886bf91d5466b416b37fdf2b6337897716e) | Active | — |
| `Voucher` (impl) | [`0x8377244a3521ff658e008df0dd40b50ca3ce534c`](https://basescan.org/address/0x8377244a3521ff658e008df0dd40b50ca3ce534c) | Active | — |
| `Voucher` proxy ("Carbon Automated Trading Strategy" NFT, `CARBON-STRAT`) | [`0x2f3b0d35830b921fe7fcd08401c6cbbe29a72dc9`](https://basescan.org/address/0x2f3b0d35830b921fe7fcd08401c6cbbe29a72dc9) | Active | — |

Source: [`alienbase-xyz/carbon-contracts`](https://github.com/alienbase-xyz/carbon-contracts) (a fork of `bancorprotocol/carbon-contracts`).

## Token Generator

Permissionless on-chain token launcher.

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| **TokenGenerator** orchestrator (collects 0.015 ETH per mint) | [`0xBcE75497D72b25c3509B62ae1a47CCfb502AD08d`](https://basescan.org/address/0xBcE75497D72b25c3509B62ae1a47CCfb502AD08d) | Active | Team deployer (team) |
| `SimpleTokenFactory` | [`0x3b01457255bD6ec460D9Ab8f31CFabd8a710D176`](https://basescan.org/address/0x3b01457255bD6ec460D9Ab8f31CFabd8a710D176) | Active | — |
| `MintableTokenFactory` | [`0x6a9668c2C6E1FB107021375BaCD9d92e79cc8369`](https://basescan.org/address/0x6a9668c2C6E1FB107021375BaCD9d92e79cc8369) | Active | — |
| `BurnableTokenFactory` | [`0xF5A7A624f4c11F581eb5a2B12e9bcA327F692c79`](https://basescan.org/address/0xF5A7A624f4c11F581eb5a2B12e9bcA327F692c79) | Active | — |
| `MintBurnTokenFactory` | [`0x872521B46095139e70A38AE3e8d95611649AAF51`](https://basescan.org/address/0x872521B46095139e70A38AE3e8d95611649AAF51) | Active | — |
| `TaxTokenFactory` | [`0x13De15f0c5E8CC78Ad3a7001bA2Cb882aaE96373`](https://basescan.org/address/0x13De15f0c5E8CC78Ad3a7001bA2Cb882aaE96373) | Active | — |
| Earlier `TaxTokenFactory` builds | `0xcbac…8436`, `0x1b24…b484`, `0x9f36…2c9f` | Superseded | Do not use |

## Governance

| Component | Address | Status | Owner |
| --- | --- | --- | --- |
| **DAO Multisig** (Gnosis Safe, 5-of-8) | [`0x4ab9070b7680f802cbf8322e597a4409902171e5`](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5) | Active | Self (multisig) |
| Snapshot space | [`alienbase-dex.eth`](https://snapshot.org/#/alienbase-dex.eth) | Active | — |
| Original AIP-2 "DAO treasury wallet" (EOA, also a Safe signer) | [`0xD9c14E5Ad86d06de762F0D179109661E5B60cC4d`](https://basescan.org/address/0xD9c14E5Ad86d06de762F0D179109661E5B60cC4d) | Historical reference | EOA |
| Snapshot strategies fork | [`alienbase-xyz/snapshot-strategies`](https://github.com/alienbase-xyz/snapshot-strategies) | Active | — |

## Deployer

The team deployer EOA is publicly tagged on Basescan as **"AlienBase: Deployer"**:

> [`0xDD3705A1c50Fc84B6d31394aA8F4D568B98a8AD5`](https://basescan.org/address/0xDD3705A1c50Fc84B6d31394aA8F4D568B98a8AD5)

It's a gas wallet with a low ETH balance; almost all of Alien Base's contracts trace back to deployments by this address. The Token Generator orchestrator routes its 0.015 ETH per-mint fee here.

## Deprecated products

These contracts are still on-chain but are no longer actively maintained or recommended. See the [Archive](archive/README.md) for context.

| Product | Sample contract | Status | Note |
| --- | --- | --- | --- |
| **Area 51** sub-DEX | Factory [`0x2d5dd5fa…e51e`](https://basescan.org/address/0x2d5dd5fa7B8a1BFBDbB0916B42280208Ee6DE51e), Router [`0x3485F8E1…79e7`](https://basescan.org/address/0x3485F8E155973cC247CBEa9E77C0dBBB4BBb79E7) | Deprecated (Oct 2024) | The Token Generator product survives separately. |
| **StableSwap** (Saddle-style) | `SwapFlashLoan` [`0x927860797d…bb27`](https://basescan.org/address/0x927860797d8CC9b94e3FdC6F1a4a3C42aDfFbb27) | Deprecated (Oct 2024) | Replaced by V3 stable-tier pools. |
| **PredictionETH** | [`0xfbe87ee1ee62244a2df80a8093eab829c52863e8`](https://basescan.org/address/0xfbe87ee1ee62244a2df80a8093eab829c52863e8) | Discontinued | Binary options MVP (2023). |
| **AlienbaseLottery** | [`0x4384dcf974769f2e0e52cde92b6d5fc9be5248ff`](https://basescan.org/address/0x4384dcf974769f2e0e52cde92b6d5fc9be5248ff) | Discontinued | ETH-ticket lottery (2023). |
| **B3 multi-chain deployment** | (B3 chain, addresses N/A) | Shelved (Oct 2025) | First multi-chain expansion; partnership did not deliver. |

## Documentation errors fixed in this revision

If you're cross-referencing the previous version of this page, note:

1. **Area 51 Router label/link mismatch** — the previous label `0x837d9B41…3376` is not a contract. The correct address is the linked one, `0x3485F8E1…79e7`.
2. **"Farm Timelock Proxy"** — the address `0x16f1F806…e4fB` is the original `DistributorController` itself, not a proxy. As of 2025-06-05 it is also no longer the active controller (replaced by `UniversalDistributorController`).
3. **"esALB-ETH pair"** — the address `0x176ca19…08f0` is a Bunni V3 LP token, not a Uniswap V2 pair.
4. **"Sample BunniToken" example** — the previous example referenced an ALB/USDbC pair. USDbC is the deprecated Coinbase-bridged USDC variant; users should reference USDC pairs instead.

## Source code

| Repo | Coverage |
| --- | --- |
| [`alienbase-xyz/alienbase-contracts`](https://github.com/alienbase-xyz/alienbase-contracts) | V2 stack + ALB token (lags onchain — last public update Nov 2024) |
| [`alienbase-xyz/area51-contracts`](https://github.com/alienbase-xyz/area51-contracts) | Area 51 V2 fork (deprecated) |
| [`alienbase-xyz/carbon-contracts`](https://github.com/alienbase-xyz/carbon-contracts) | Bancor Carbon fork |
| [`alienbase-xyz/Mothership`](https://github.com/alienbase-xyz/Mothership) | Mothership ALM (under audit) |
| [`alienbase-xyz/snapshot-strategies`](https://github.com/alienbase-xyz/snapshot-strategies) | Custom esALB voting strategies |
| [`alienbase-xyz/DefiLlama-Adapters`](https://github.com/alienbase-xyz/DefiLlama-Adapters) | TVL adapter contributions |

Several deployed contracts (TokenGenerator, EsProxyMaster, EsTokenController, EsVoting, EsComplexRewarder, UniversalDistributorController, VestingFactory, AlienbaseLottery, PredictionETH, AlienbaseZapV1, the recent Alien Base 2.0 rollout) are **verified on Basescan** but their source repositories are not yet public. This is on the roadmap to fix.
