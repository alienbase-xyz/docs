---
description: ALB tokenomics, emission history, and value flow
---

# ALB Token

ALB is the native token of Alien Base — used for governance, staking, liquidity incentives, and the platform's Real Yield rewards system.

> *Last updated: {{today}}.*

## At a glance

| | |
| --- | --- |
| Token contract | [`0x1dd2d631c92b1aCdFCDd51A0F7145A50130050C4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) |
| Standard | ERC-20 (18 decimals), OpenZeppelin AccessControl |
| Network | Base (chain id 8453) |
| Token Generation Event | August 8, 2023 |
| Current max supply | 510,000,000 ALB |
| Currently minted | ~467,000,000 ALB (~91.6% of cap) <!-- as of 2026-06-30, CoinGecko --> |
| Circulating supply | ~236,000,000 ALB (~46% of cap) <!-- as of 2026-06-30, CoinGecko --> |
| Mint timelock | 14 days (no insider mint without delay) |

For up-to-date market data: [CoinGecko](https://www.coingecko.com/en/coins/alienbase) · [DexScreener](https://dexscreener.com/base/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) · [DefiLlama](https://defillama.com/protocol/alien-base-v3).

## What ALB is for

- **Governance.** ALB locked into [esALB](escrowed-alb-esalb/README.md) carries voting power on Snapshot. Soon, [govALB](#alien-base-2-0-aip-5) will offer 10× voting weight in exchange for a 2-year lock.
- **Real Yield.** esALB stakers earn a share of protocol fees, paid in **WETH** and other liquid assets — not in extra ALB. This is the heart of the value-distribution model: the protocol's revenue goes back to long-term holders.
- **Liquidity incentives.** Active LPs in V2 and V3 vaults earn ALB emissions on top of pool fees. (Note: [AIP-5](https://snapshot.org/#/alienbase-dex.eth/proposal/0x9328ecc5a0d2527a1e73fd30085e7ba2120a985b7782ce843f15ee2ddf38ca63) replaces farming with a Protocol-Owned-Liquidity model — see below.)
- **Single-staking.** Lock ALB → esALB and stake esALB to earn unlocked ALB rewards.

## Emission history

Alien Base's emission schedule has changed several times since launch as the DAO matured. The numbers below are the actual schedule in effect, not the original launch-day plan.

| Date | Rate | Trigger |
| --- | --- | --- |
| 2023-08-08 | 15 ALB/sec (launch) | TGE |
| 2023-08-19 | **8 ALB/sec** | [AIP-1 (de facto)](https://snapshot.org/#/alienbase-dex.eth/proposal/0x56c418fd7f7fd365b0beba44389807941e3150fb376179ac758fb497f04a999b) — emergency 46% cut after sniper bots captured the initial liquidity supply |
| 2023-11-27 | 10.5 ALB/sec (briefly), then tapered toward 7.5 | [AIP-2](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52) — V3 launch boost program |
| 2024-09 | **3.75 ALB/sec** | 2nd halving — confirmed in [AIP-3](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd) |
| 2025-06 | ~1.875 ALB/sec (yearly inflation 30% → 15%) | 3rd halving — confirmed in the [Oct 2025 roadmap retrospective](https://medium.com/@alienbase/alien-base-roadmap-plotting-the-next-phase-of-the-invasion-11ede525e2ea) |
| 2026-04 | **Flexible emissions, no fixed halving** | [AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — replaces farming with POL fund + buyback-and-burn |

Today, **~91.6% of the original 510M cap has been minted** (~467M ALB, of which ~236M circulates and the rest is locked as esALB). The team cannot mint additional ALB without going through the 14-day timelock; farming emission parameters are also timelocked for 7 days.

> The original "halving every 9 months" schedule was a launch-time plan. As the project matured, the DAO adjusted the path twice (AIP-3, AIP-4) to align emissions with revenue, and finally replaced the halving model entirely (AIP-5) with a flexible system tied to protocol earnings.

## Value flow (Real Yield)

```
            Trading on Alien Base
                      │
                      ▼
              Pool fees (V2 / V3)
                      │
        ┌─────────────┼─────────────┐
        ▼             ▼             ▼
       LPs       Protocol share   Carbon makers
        │             │           (keep their spread)
        │             │
        │             ▼
        │     ┌───────┴─────────────────┐
        │     ▼               ▼         ▼
        │  esALB stakers    DAO     POL Fund
        │  (Real Yield in   treasury  (per AIP-5,
        │  WETH + tokens)             buyback & burn)
        ▼
      LP rewards (ALB emissions, ramping down per AIP-5)
```

Per [AIP-2](https://snapshot.org/#/alienbase-dex.eth/proposal/0xea788bd0daf9fb61acb0199874abc56f9c871cc2e117c3c1c11a45ba1ced7f52), 40% of V3 protocol fees are routed to ALB and esALB stakers, with the remaining share funding the DAO and (under AIP-5) the POL fund.

The full fee table — V2, V3 tiers, Epsilon, Carbon, DCA, Token Generator — is on the [Fees](fees.md) page.

## Initial supply & distribution

The initial 26 million ALB (~5.1% of the cap) was minted at launch, of which 1 million seeded the original V2 launch liquidity pool. The remaining 25 million was directed to a timelock contract because sniper-bot activity made the planned full liquidity-pool seed impossible at launch.

| Bucket | Size | Use |
| --- | --- | --- |
| Initial mint | 26 M | 1 M seeded V2 launch LP; 25 M sent to timelock |
| Timelock allocation — growth | 20 M | Fundraising, marketing, market-making for ALB liquidity |
| Timelock allocation — team | 5 M | Distributed to the team via vesting contracts (deployed as `VestingFactory` in 2025-06; see [Vesting](escrowed-alb-esalb/vesting.md)) |
| Farming emissions — team | 15% of new emissions | Operating budget (salaries, infra) — paid out via DAO vote |
| Farming emissions — DAO | 15% of new emissions (raised to 20% in [AIP-3](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd)) | Long-term treasury & marketing |

The original timelock transactions for the 25 M are at:
- [`0x44d3753e…aca9`](https://basescan.org/tx/0x44d3753e8e0e104f4751665af885c77fc8ee338abd377496cb33b1a35b10aca9)
- [`0x59365156…d278`](https://basescan.org/tx/0x5936515cc428ce9d66396d995b490f059da4152c182e1e8f42dc7ce6a38fd278)
- [`0x079a3f09…540d`](https://basescan.org/tx/0x079a3f09c533fd61768cfb88d2fdf21effd67c4311819974ddc446b342b5540d)

## DAO operating budget (current)

The team has a transparent monthly budget approved by DAO vote. The current cycle is governed by [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) (Sept 2025 → Feb 2026):

- $200,000 USDC reserve, allocated as Infrastructure $48k / Liquidity & Incentives $40k / Strategic Savings $112k
- $42,500 revenue-funded growth: Dev & Security $15k, Legal $12.5k, Marketing $10k, Grants $5k
- 1,000,000 ALB/month dev allowance + 1,000,000 ALB/month POL contribution

The team uses bots to TWAP-sell its ALB allocation slowly — both to avoid impacting price and to keep sells unpredictable to MEV. There's no scheduled cliff and no surprise dump.

## Alien Base 2.0 (AIP-5)

[AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — passed April 2026 — is a full tokenomics rewrite. Highlights:

- **Replaces farming with a Protocol-Owned-Liquidity (POL) Fund.** Stablecoins, blue chips, Base-native assets, and Alien Base LPs. POL yield is used for buyback-and-burn ALB.
- **Replaces fixed halvings with flexible emissions** tied to protocol earnings.
- **Dev Line of Credit (LoC):** the dev allowance becomes tracked debt with interest paid to esALB holders. Price-tier grant tranches at $0.40, $1, and $2 (via moving averages) unlock dev funding only when ALB sustains those price levels.
- **Splits governance** into **Alien Base DAO** (governs onchain contracts) and **Alien Labs** (offchain product, frontend, revenue).
- **govALB:** a new staked-escrow form of esALB with **10× voting power**, 1× earning power, and a ~2-year effective lock.
- **Supply cap raised** (one-time) from **510,000,000 → 1,051,000,000** ALB. Direct allocation increase = 200M; remainder reserved for esALB protection program and strategic allocations. Expected actual supply post-rollout: ≤ 800M.

Implementation is rolling out now; see [Roadmap](roadmap.md) and [Alien Base 2.0](alien-base-2-0.md) for current status.

## ALB liquidity

ALB is traded across multiple Base DEXes. As of {{today}} there are 27 ALB pairs across all venues, dominated by:

- **Alien Base** — 20 pools (~$281K total liquidity), most active being ALB/WETH at [`0xbcd2…6fcB`](https://basescan.org/address/0xbcd27A437eBe92555Cee6b5bBeDdAC639a1b6fcB).
- **Uniswap** — 3 pools.
- **Aerodrome / SwapBased / others** — small parallel liquidity.

If you swap on Alien Base, [Epsilon](trading/epsilon.md) routes through whichever venue gives the best price (almost always the native pools).

## Resources

- ALB on Basescan: [`0x1dd2d631…50c4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4)
- Source code: [`alienbase-xyz/alienbase-contracts`](https://github.com/alienbase-xyz/alienbase-contracts)
- Tokenomics articles on Medium:
  - [Strategic Roadmap Update for Alien Base](https://medium.com/@alienbase/strategic-roadmap-update-for-alien-base-c569f2bfcc46) — Sep 2023
  - [Introducing EsALB: The Next Phase of Alien Base Tokenomics](https://medium.com/@alienbase/introducing-esalb-the-next-phase-of-alien-base-tokenomics-e5bfa049486f) — Apr 2024
  - [AIP-3: Establishing DAO Budget for 2nd Halving Cycle](https://medium.com/@alienbase/aip-3-establishing-dao-budget-for-2nd-halving-cycle-8092e0039cfd) — Oct 2024
  - [AIP-5: Building Alien Base 2.0](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) — Mar 2026
