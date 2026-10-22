---
description: The AIP-5 tokenomics rewrite, in plain language
---

# Alien Base 2.0 (AIP-5)

**Alien Base 2.0** is the package of tokenomics and governance changes authorized by [AIP-5](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63) (passed April 2026). It replaces the old "halving farming model" with a new model built around Protocol-Owned Liquidity, a Dev Line of Credit, and a clearer DAO / Foundation / Labs split.

> _Last updated: October 22, 2026._ The new token contracts are live and the 1:1 migration is open. This page tracks the moving pieces.

{% hint style="info" %}
**Holding old ALB or esALB?** Swap it 1:1 for the new tokens at [app.alienbase.xyz/migration](https://app.alienbase.xyz/migration). There's no deadline. See the [Migration Guide](migration/README.md).
{% endhint %}

## The changes at a glance

1. **Farming → POL.** Farming emissions wind down. A Protocol-Owned-Liquidity (POL) Fund takes over as the primary liquidity-provision mechanism.
2. **Halvings → flexible emissions.** The old fixed-halving schedule retires. Emissions are sized to revenue, with headroom kept on the upside if needed.
3. **Dev allowance → Line of Credit.** Team funding becomes tracked debt with interest paid back to esALB holders. Price-tier grants at $0.40, $1, $2 unlock as ALB sustains those moving averages.
4. **govALB.** New staked-escrow tier with **10× voting power**, 1× earning power, \~2-year effective lock.
5. **Supply cap raised.** One-time bump from **510,000,000 → 1,051,000,000 ALB**. Direct allocation increase = 200M; remainder reserved for esALB protection program and strategic allocations. Expected actual supply post-rollout: ≤ 800M.
6. **New token contracts + 1:1 migration.** ALB, esALB and govALB are redeployed as a new token system with the 1.051B cap built in. Legacy ALB and esALB swap 1:1, with no deadline.

## Why each piece matters

### POL Fund

Farming subsidies are the most expensive form of liquidity a protocol can buy. Every block, the protocol prints ALB and gives it to LPs. As the price recovers, the LPs typically sell — extracting value from the protocol.

The POL Fund flips this:

* The DAO holds the liquidity itself (stablecoins, blue chips, Base-native assets, Alien Base LPs).
* Yield from POL is used for **buyback-and-burn ALB**.
* Net result: liquidity stays on the platform, ALB supply grows more slowly (or shrinks during high-volume periods), and the protocol keeps the value its trading volume generates.

### Flexible emissions

Halvings were a clean concept but rigid. They didn't respond to market conditions, treasury health, or demand. AIP-5 replaces them with **emissions that scale with protocol revenue** and that can be adjusted via governance more dynamically. Emissions never run away because they're capped by supply.

### Line of Credit

Treasury-to-team funding was previously a flat allowance — emit X ALB/month for the dev budget. Two issues:

* It was static. If ALB price 10x'd, the dev team got 10x the funding regardless of need.
* It was untracked. There was no formal accounting of what the DAO had funded.

The Line of Credit fixes both. Every ALB drawn for dev funding is **tracked debt**. esALB holders receive interest and dilution protection on the outstanding LoC — projected \~30–35% APR at expected operating volumes. Debt clears via **price-tier grants**: when ALB sustains $0.40, $1, or $2 (moving averages), a tranche unlocks as a grant rather than debt. This aligns Labs's funding with protocol value creation.

### govALB

esALB is great for one-eyed governance ("my voice matters" while my ALB is locked) — but it's still relatively short-term commitment. Many of the protocol's biggest decisions (tokenomics, multi-year roadmap) deserve input from holders with longer time horizons.

govALB is the long-time-horizon tier. **10× voting weight** in exchange for a roughly 2-year effective lock. Earning rate stays 1× — govALB doesn't print extra rewards, just amplifies governance weight.

### Supply cap raise

The old 510M cap was set in 2023 and has been \~90% emitted. Rather than letting issuance crash to zero (and starving the protocol of incentives at the moment Mothership and Epsilon Router go live), the cap is raised once to 1.051 B.

The raise was delivered through the new ALB contract, where `MAX_SUPPLY` is hard-coded at **1,051,000,000**, rather than by modifying the legacy token. New ALB is only minted 1:1 against migrated legacy tokens or as Distributor emissions, so the new supply tracks migration and never exceeds the cap.

Important: the cap is a **ceiling**, not a target. The expected actual supply post-rollout is **≤ 800 M**. The 200 M direct allocation increase covers the next phase of growth; the remainder is reserved for the **esALB protection program** (preserving APR for esALB holders during the transition) and **strategic allocations** (POL seeding, partner integrations, future grants).

### New contracts and migration

Moving to new contracts let AIP-5 ship as a clean system instead of a patch on the 2023 stack:

* **ALB** ([`0x1b23…cef7`](https://basescan.org/token/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7)): hard cap of 1.051B, mintable only by the Migration Contract and the farm Distributor, burnable.
* **esALB** ([`0x32d9…4473`](https://basescan.org/token/0x32d9f29170a023794025375df6949f56844e4473)): earns automatically while held; 30 to 60 day exit (85% → 100%); small instant-redeem allowance. See [esALB](escrowed-alb-esalb/).
* **govALB** ([`0x7fdb…441d`](https://basescan.org/token/0x7fdb2cbe3dd946b6b4521d4a2cce62296ec1441d)): 2-year lock, 10× voting power, converted 1:1 from esALB. See [govALB](escrowed-alb-esalb/#govalb).
* **Staking contract**: pays ALB and WETH rewards to esALB and govALB holders, share for share.
* **Distributor**: the new multi-stream farm that replaces the MasterChef-era farms.
* **Migration Contract** ([`0xa53d…9d3d`](https://basescan.org/address/0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d)): swaps legacy ALB and esALB 1:1 and locks the legacy tokens forever. No owner, no deadline.

Every address is on the [Contracts](contracts.md#new-token-system-aip-5) page. How to move your tokens: [Migration Guide](migration/README.md) · [FAQ](migration/faq.md).

## DAO / Foundation / Labs split

AIP-5 also formalized the org structure:

* **Alien Base DAO** — the on-chain authority. Holds privileged roles on the protocol contracts. Ratifies major decisions via Snapshot.
* [**Alien Foundation**](alien-base-dao/alien-foundation.md) — Cayman-registered, ownerless legal entity. Holds offchain assets (USDC reserves, vendor relationships, audit engagements). Acts on behalf of the DAO when an offchain counterparty is required.
* [**Alien Labs**](alien-base-dao/alien-labs.md) — operational arm. Builds the dApp, designs and ships products, runs commercial operations. Funded via the LoC.

The DAO remains the supreme authority over the protocol contracts, while Labs takes care of user-facing and Web2-based portions of the protocol.

## Rollout timeline

| Phase                    | What happens                                                             | Status                                         |
| ------------------------ | ------------------------------------------------------------------------ | ---------------------------------------------- |
| Vote                     | AIP-5 passes Snapshot                                                    | Done (Apr 7, 2026)                             |
| Onchain deployments      | New ALB, esALB, govALB, staking, Distributor, LoC factory, price oracles and Migration Contract deployed; owned by the 7-day TimelockController | Done                                           |
| Cap raise                | Delivered via the new ALB contract (`MAX_SUPPLY` = 1,051,000,000)          | Done                                           |
| Token migration          | Legacy ALB / esALB → new ALB / esALB, 1:1, no deadline                    | **Live** ([migrate](https://app.alienbase.xyz/migration)) |
| Supply API               | Public total and circulating supply endpoints                            | Live (see [ALB Token](alb-token.md#supply-api)) |
| Farming wind-down        | Existing farms deprecated, replaced by Vaults / POL flows                | In progress                                    |
| esALB protection program | APR-stabilization for esALB holders during transition                    | Pending                                        |
| Public dashboards        | LoC drawdown tracker, POL holdings, buyback-and-burn cadence             | Planned                                        |

## See also

* [AIP-5 — Building Alien Base 2.0](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — the full proposal.
* [Snapshot vote](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63)
* [ALB Token](alb-token.md)
* [Migration Guide](migration/README.md) and [Migration FAQ](migration/faq.md)
* [Roadmap](roadmap.md)
* [Alien Foundation](alien-base-dao/alien-foundation.md) and [Alien Labs](alien-base-dao/alien-labs.md)
