---
description: ALB tokenomics, emission history, and value flow
---

# ALB Token

ALB is the native token of Alien Base — used for governance, staking, liquidity incentives, and the platform's Real Yield rewards system.

> _Last updated: October 22, 2026._

{% hint style="warning" %}
**ALB has moved to a new contract.** Under [AIP-5](alien-base-2-0.md), ALB and esALB were redeployed as part of Alien Base 2.0. Old ALB and old esALB swap **1:1** for the new tokens, with no deadline. See the [Migration Guide](migration/README.md).
{% endhint %}

## At a glance

|                        |                                                                                                                                  |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Token contract         | [`0x1b23704e3f4bc7081fb00cec582183e3fe43cef7`](https://basescan.org/token/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7)            |
| Name / symbol          | Alien Base Token / ALB                                                                                                           |
| Standard               | ERC-20, 18 decimals, burnable                                                                                                    |
| Network                | Base (chain id 8453)                                                                                                             |
| Max supply             | **1,051,000,000 ALB**, hard-coded in the contract (`MAX_SUPPLY`)                                                                 |
| Who can mint           | Only whitelisted minters: the [Migration Contract](migration/README.md) and the new farm Distributor, never above the cap         |
| Admin                  | 7-day [TimelockController](https://basescan.org/address/0x1c7e4284423c1a2362c49b1ea223b73e38c81e21); ownership can't be renounced |
| Live supply            | [Supply section](#supply) below, or the [public supply API](#supply-api)                                                         |
| Legacy token           | [`0x1dd2d631…50C4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) (TGE August 8, 2023), migrates 1:1   |

For market data: [DexScreener (new ALB)](https://dexscreener.com/base/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7) · [CoinGecko](https://www.coingecko.com/en/coins/alienbase) · [DefiLlama](https://defillama.com/protocol/alien-base-v3). Trackers are being switched to the new contract; until they are, some may still show the legacy token.

## What ALB is for

* **Governance.** ALB locked into [esALB](escrowed-alb-esalb/) carries voting power on Snapshot. [govALB](escrowed-alb-esalb/#govalb) offers 10× voting weight in exchange for a 2-year lock.
* **Real Yield.** esALB stakers earn a share of protocol fees, paid in **WETH** and other liquid assets — not in extra ALB. This is the heart of the value-distribution model: the protocol's revenue goes back to long-term holders.
* **Liquidity incentives.** Active LPs in V2 and V3 vaults earn ALB emissions on top of pool fees. (Note: [AIP-5](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63) replaces farming with a Protocol-Owned-Liquidity model — see below.)
* **Single-staking.** Lock ALB → esALB (or govALB). Holding it is enough to earn ALB and WETH rewards; there's no separate staking step on the new contracts.

## Supply

The new ALB starts from zero and is minted only in two ways: **1:1 against migrated legacy ALB / esALB**, and **emissions** through the new farm Distributor. Both are bounded by the hard cap of **1,051,000,000 ALB**. Legacy ALB that is migrated is locked in the Migration Contract forever, so it leaves circulation as the new supply grows.

### Circulating supply definition

**Circulating supply = total supply − ALB backing new esALB − ALB backing govALB − ALB held by the [DAO Multisig](alien-base-dao/dao-multisig.md).**

esALB and govALB are fully backed by ALB held inside their contracts, so that ALB is locked rather than circulating. The DAO Multisig's ALB is treasury, not float.

### Snapshot (October 22, 2026)

| Metric                             | Value                     |
| ---------------------------------- | ------------------------- |
| Max supply                         | 1,051,000,000 ALB         |
| Total supply (new ALB)             | \~653,416 ALB             |
| ALB backing new esALB              | \~1,832 ALB               |
| ALB backing govALB                 | 160 ALB                   |
| Legacy ALB migrated so far         | \~349,693 ALB             |
| Legacy esALB migrated so far       | \~1,983 esALB             |
| Legacy ALB total supply            | \~485,407,206 ALB         |

These numbers move every time someone migrates. Use the API below or read the contracts for live values.

### Supply API

Public endpoints for trackers and integrators. They return plain numbers in whole ALB (not wei):

| Endpoint | Returns |
| --- | --- |
| [`/prod/circulating`](https://sxxtwqn1v0.execute-api.eu-central-1.amazonaws.com/prod/circulating) | Circulating supply |
| [`/prod/total`](https://sxxtwqn1v0.execute-api.eu-central-1.amazonaws.com/prod/total) | Total supply |
| [`/prod/supply`](https://sxxtwqn1v0.execute-api.eu-central-1.amazonaws.com/prod/supply) | JSON with both: `{"totalSupply": "...", "circulatingSupply": "..."}` |

Base URL: `https://sxxtwqn1v0.execute-api.eu-central-1.amazonaws.com`.

On-chain sources: `totalSupply()` on [ALB](https://basescan.org/token/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7#readContract); ALB `balanceOf` the [esALB](https://basescan.org/token/0x32d9f29170a023794025375df6949f56844e4473) and [govALB](https://basescan.org/token/0x7fdb2cbe3dd946b6b4521d4a2cce62296ec1441d) contracts; `totalLegacyALBLocked()` / `totalLegacyEsALBLocked()` on the [Migration Contract](https://basescan.org/address/0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d#readContract).

## Emission history

Alien Base's emission schedule has changed several times since launch as the DAO matured. The numbers below are the actual schedule in effect, not the original launch-day plan.

| Date       | Rate                                            | Trigger                                                                                                                                                                                                              |
| ---------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 2023-08-08 | 15 ALB/sec (launch)                             | TGE                                                                                                                                                                                                                  |
| 2023-08-19 | **8 ALB/sec**                                   | [AIP-1 (de facto)](https://snapshot.org/#/alienbase-dex.eth/proposal/0x56c418fd7f7fd365b0beba44389807941e3150fb376179ac758fb497f04a999b) — emergency 46% cut after sniper bots captured the initial liquidity supply |
| 2023-11-27 | 10.5 ALB/sec (briefly), then tapered toward 7.5 | [AIP-2](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52) — V3 launch boost program                                                              |
| 2024-09    | **3.75 ALB/sec**                                | 2nd halving — confirmed in [AIP-3](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd)                                                                                   |
| 2025-06    | \~1.875 ALB/sec (yearly inflation 30% → 15%)    | 3rd halving — confirmed in the [Oct 2025 roadmap retrospective](https://medium.com/@alienbase/alien-base-roadmap-plotting-the-next-phase-of-the-invasion-11ede525e2ea)                                               |
| 2026-04    | **Flexible emissions, no fixed halving**        | [AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — replaces farming with POL fund + buyback-and-burn                                                                                |

By mid-2026, **\~91% of the legacy token's 510M cap had been minted** (\~465M ALB, of which \~234M circulated and the rest was locked as esALB). That near-exhausted cap is one of the reasons AIP-5 moved ALB to a new contract with a 1.051B cap. On the legacy token, minting went through a 14-day timelock; on the new token, admin changes go through the 7-day TimelockController and minting is limited to the Migration Contract and the Distributor.

> The original "halving every 9 months" schedule was a launch-time plan. As the project matured, the DAO adjusted the path twice (AIP-3, AIP-4) to align emissions with revenue, and finally replaced the halving model entirely (AIP-5) with a flexible system tied to protocol earnings.

## Value flow (Real Yield)

```
            Trading on Alien Base
                      │
                      ▼
              Pool fees (V2 / V3)
                      │
        ┌─────────────┼──────────────┐
        ▼             ▼              ▼
       LPs       Protocol share   Epsilon fees
        │             │           (swaps + orders)
        │             │              │
        │             ▼◄─────────────┘
        │     ┌───────┴─────────────────┐
        │     ▼               ▼         ▼
        │  esALB stakers    DAO     POL Fund
        │  (Real Yield in   treasury  (per AIP-5,
        │  WETH + tokens)             buyback & burn)
        ▼
      LP rewards (ALB emissions, ramping down per AIP-5)
```

V3 pool fees are split **50/50 between LPs and esALB stakers**; Epsilon swap and order fees accrue entirely to the protocol share, which funds the esALB Real Yield stream, the DAO treasury, and (under AIP-5) the POL fund.

The full fee table — V2, V3 tiers, Epsilon swaps, Epsilon Router orders (Limit / Stop / Trailing Stop / DCA), Token Generator — is on the [Fees](fees.md) page.

## Initial supply & distribution

_This section describes the legacy token's launch in 2023. The new token's supply comes entirely from migration and Distributor emissions; see [Supply](#supply)._

The initial 26 million ALB (\~5.1% of the cap) was minted at launch, of which 1 million seeded the original V2 launch liquidity pool. The remaining 25 million was directed to a timelock contract because sniper-bot activity made the planned full liquidity-pool seed impossible at launch.

| Bucket                       | Size                                                                                                                                            | Use                                                                                                                                   |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| Initial mint                 | 26 M                                                                                                                                            | 1 M seeded V2 launch LP; 25 M sent to timelock                                                                                        |
| Timelock allocation — growth | 20 M                                                                                                                                            | Fundraising, marketing, market-making for ALB liquidity                                                                               |
| Timelock allocation — team   | 5 M                                                                                                                                             | Distributed to the team via vesting contracts (deployed as `VestingFactory` in 2025-06; see [Vesting](escrowed-alb-esalb/vesting.md)) |
| Farming emissions — team     | 15% of new emissions (lowered to 10% in AIP-3)                                                                                                  | Operating budget (salaries, infra, incentivization)                                                                                   |
| Farming emissions — DAO      | 15% of new emissions (raised to 20% in [AIP-3](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd)) | Long-term treasury & marketing                                                                                                        |

The original timelock transactions for the 25 M are at:

* [`0x44d3753e…aca9`](https://basescan.org/tx/0x44d3753e8e0e104f4751665af885c77fc8ee338abd377496cb33b1a35b10aca9)
* [`0x59365156…d278`](https://basescan.org/tx/0x5936515cc428ce9d66396d995b490f059da4152c182e1e8f42dc7ce6a38fd278)
* [`0x079a3f09…540d`](https://basescan.org/tx/0x079a3f09c533fd61768cfb88d2fdf21effd67c4311819974ddc446b342b5540d)

## DAO operating budget (current)

The team has a transparent monthly budget approved by DAO vote. The most recent published cycle was governed by [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) (Sept 2025 → Feb 2026); team funding is transitioning to the [AIP-5 Line-of-Credit model](alb-token.md#alien-base-2-0-aip-5). The ADIP-01 structure:

* $200,000 USDC reserve, allocated as Infrastructure $48k / Liquidity & Incentives $40k / Strategic Savings $112k
* $42,500 revenue-funded growth: Dev & Security $15k, Legal $12.5k, Marketing $10k, Grants $5k
* 1,000,000 ALB/month dev allowance + 1,000,000 ALB/month POL contribution

The team uses bots to TWAP-sell its ALB allocation slowly — both to avoid impacting price and to keep sells unpredictable to MEV. There's no scheduled cliff and no surprise dump.

## Alien Base 2.0 (AIP-5)

[AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — passed April 2026 — is a full tokenomics rewrite. Highlights:

* **Replaces farming with a Protocol-Owned-Liquidity (POL) Fund.** Stablecoins, blue chips, Base-native assets, and Alien Base LPs. POL yield is used for buyback-and-burn ALB.
* **Replaces fixed halvings with flexible emissions** tied to protocol earnings.
* **Dev Line of Credit (LoC):** the dev allowance becomes tracked debt with interest paid to esALB holders. Price-tier grant tranches at $0.40, $1, and $2 (via moving averages) unlock dev funding only when ALB sustains those price levels.
* **Splits governance** into **Alien Base DAO** (governs onchain contracts) and **Alien Labs** (offchain product, frontend, revenue).
* **govALB:** a new staked-escrow form of esALB with **10× voting power**, 1× earning power, and a \~2-year effective lock.
* **Supply cap raised** (one-time) from **510,000,000 → 1,051,000,000** ALB. Direct allocation increase = 200M; remainder reserved for esALB protection program and strategic allocations. Expected actual supply post-rollout: ≤ 800M.
* **New token contracts.** Rather than modifying the legacy token, the new cap and mechanics ship as a fresh ALB, esALB and govALB, with a 1:1 [migration](migration/README.md) from the legacy tokens.

The new contracts are live and migration is open. See [Alien Base 2.0](alien-base-2-0.md) for the rollout status.

## ALB liquidity

**New ALB** trades on Alien Base V3. Pools as of October 22, 2026:

* ALB/WETH: [`0xFF43…F1B7`](https://basescan.org/address/0xFF4364b623dC4D9A1556774467748EAb68DfF1B7)
* ALB/USDC: [`0x4867…c97d`](https://basescan.org/address/0x48676681A1F5BefD4b79273BdA2D85cD5390c97d)

Live list: [DexScreener (new ALB)](https://dexscreener.com/base/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7).

**Legacy ALB** still trades while holders migrate. As of July 6, 2026 it had \~27 pairs across Base DEXes, led by the Alien Base V3 ALB/WETH pool at [`0xbcd2…6fcB`](https://basescan.org/address/0xbcd27A437eBe92555Cee6b5bBeDdAC639a1b6fcB), plus Uniswap (3 pools) and smaller venues. Legacy ALB bought anywhere can be [migrated](migration/README.md) 1:1.

If you swap on Alien Base, [Epsilon](trading/epsilon.md) routes through whichever venue gives the best price. Always check which ALB contract you're buying.

## Resources

* ALB on Basescan: [`0x1b23704e…cef7`](https://basescan.org/token/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7) (legacy: [`0x1dd2d631…50c4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4))
* [Migration Guide](migration/README.md) and [Migration FAQ](migration/faq.md)
* Source code: legacy contracts at [`alienbase-xyz/alienbase-contracts`](https://github.com/alienbase-xyz/alienbase-contracts); the Alien Base 2.0 contracts are verified on Basescan (see [Contracts](contracts.md#new-token-system-aip-5))
* Tokenomics articles on Medium:
  * [Strategic Roadmap Update for Alien Base](https://medium.com/@alienbase/strategic-roadmap-update-for-alien-base-c569f2bfcc46) — Sep 2023
  * [Introducing EsALB: The Next Phase of Alien Base Tokenomics](https://medium.com/@alienbase/introducing-esalb-the-next-phase-of-alien-base-tokenomics-e5bfa049486f) — Apr 2024
  * [AIP-3: Establishing DAO Budget for 2nd Halving Cycle](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd) — Oct 2024
  * [AIP-5: Building Alien Base 2.0](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — Mar 2026
