---
description: Where to find live data on Alien Base — token, trading, liquidity, holders
---

# Data & Analytics

Alien Base data is published live across several venues. The **Dune dashboard maintained by Sealaunch** is the canonical, team-developed source — start there for anything that requires depth (per-pair volume, holder analysis, esALB lock/unlock flows, DEX benchmark comparisons). External market-data sites are still useful for headline numbers and price tracking.

> *Last updated: July 6, 2026.*

## Market snapshot

Point-in-time figures, refreshed manually. Treat these as a sanity check, not live data — click through to the source for the current number.

| Metric | Value | As of | Source |
| --- | --- | --- | --- |
| ALB price | ~$0.0047 | 2026-07-06 | [CoinGecko](https://www.coingecko.com/en/coins/alienbase) |
| Market cap | ~$1.12M | 2026-07-06 | [CoinGecko](https://www.coingecko.com/en/coins/alienbase) |
| Fully-diluted valuation | ~$2.23M | 2026-07-06 | [CoinGecko](https://www.coingecko.com/en/coins/alienbase) |
| Circulating supply | ~234M ALB | 2026-07-06 | [CoinGecko](https://www.coingecko.com/en/coins/alienbase) |
| Total minted supply | ~465M ALB (~91% of the 510M cap) | 2026-07-06 | [Basescan](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) |
| All-time high | $0.5724 on 2024-11-27 (−99% from ATH) | 2026-07-06 | [CoinGecko](https://www.coingecko.com/en/coins/alienbase) |
| TVL | ~$1.63M pooled + ~$1.04M staked | 2026-07-06 | [DefiLlama](https://defillama.com/protocol/alien-base) |
| Deepest pool | ALB/WETH on Alien Base, ~$172k liquidity | 2026-07-06 | [DexScreener](https://dexscreener.com/base/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) |

> **esALB share, holder counts, per-pair volume, lifetime trades/users, and protocol-fee totals** are not exposed by these public APIs — read them off the [Dune dashboard](https://dune.com/sealaunch/alienbase) (`ALB Token & esALB` and `Alien Base Overview` panels) and update the [Welcome page](README.md) Quick Stats when they move materially. <!-- TODO:USER refresh esALB-locked %, holder counts, lifetime users from Dune -->

## Canonical dashboard — Dune (Sealaunch)

**[dune.com/sealaunch/alienbase](https://dune.com/sealaunch/alienbase)** — the official Alien Base analytics dashboard, developed in partnership with [Sealaunch](https://www.sealaunch.xyz/).

What's on it:

| Section | Includes |
| --- | --- |
| **Alien Base Overview** | 30-day trades, 30-day unique addresses, 30-day volume ($), cumulative trades, addresses trading, average trade value, average value per trader |
| **DEX Activity Benchmark** | Cross-DEX comparison (3-month moving average via DefiLlama) — trades per user, average trade size, average volume per address, % low-value txs (< $0.10), % HFT addresses (>1,000 txs/day) |
| **Top Traded Pairs** | Per-pair: trades, volume in $, volume %, unique addresses trading. Includes a "Top DEX Token Pairs List" table; a `Δ = Infinity` flag indicates a newly-launched pair |
| **ALB Token & esALB** | $ALB price, ALB Max Supply, current Supply, Circulating (Supply − esALB), ALB in esALB, ALB locked on esALB, Mcap, ALB holders, esALB holders, Total Holders (ALB + esALB), Top 100 ALB + esALB holders |
| **esALB lock/unlock flows** | Daily ALB → esALB and esALB → ALB activity |
| **Fees** | Protocol fees collected over time |

Best for: deep dives, cross-DEX benchmarking, token-distribution analysis, governance research, and "is the protocol healthy?" questions.

## In-app — Explorer

Inside [app.alienbase.xyz](https://app.alienbase.xyz) → **Explorer** in the sidebar ([/info](https://app.alienbase.xyz/info)). Chain-wide token & pool explorer powered by Alien Base's own data layer (the same one Epsilon uses for routing). Includes GoPlus-powered token safety checks per token.

Best for: live exploration of any token or pool on Base from inside the dApp. See [Explorer](trading/epsilon-analytics.md).

## Headline numbers — DefiLlama

**[defillama.com/protocol/alien-base-v3](https://defillama.com/protocol/alien-base-v3)** — TVL, fees, trading volume per protocol entry. DefiLlama lists multiple Alien Base entries (V2, V3, deprecated Area 51 and StableSwap); roll them up if you want the headline TVL.

Best for: headline TVL, fees-collected, lifetime-volume figures.

## Token tracking

| Site | Use |
| --- | --- |
| [CoinGecko](https://www.coingecko.com/en/coins/alienbase) | Price, market cap, fully-diluted valuation, social links, watchlists |
| [DexScreener](https://dexscreener.com/base/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) | Every ALB pool on every DEX on Base, live trade tape |
| [GeckoTerminal](https://www.geckoterminal.com/) | Alternate pool view; cleaner charts on illiquid pairs |
| [CoinMarketCap](https://coinmarketcap.com/currencies/alien-base/) | Price, supply, and market-cap tracking (listed since launch year) |

## On-chain explorers

- **[Basescan](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4)** — primary explorer for Base. Token holders, transfers, contract reads/writes.
- **[Blockscout](https://base.blockscout.com/)** — alternative explorer; sometimes faster on read-only queries; native API isn't blocked by Cloudflare.

## Governance & treasury

- **[Snapshot space](https://snapshot.org/#/alienbase-dex.eth)** — every AIP / ADIP, vote results, current voting power.
- **[DAO Multisig on Safe](https://app.safe.global/home?safe=base:0x4ab9070b7680f802cbf8322e597a4409902171e5)** — live treasury composition and pending Safe transactions.

## Repos

- **[github.com/alienbase-xyz](https://github.com/alienbase-xyz/)** — public source code for the contracts + apps that have public repos. (Not every deployed contract has a public repo; we're working on improving this — see [Audits & Security](audits-and-security.md).)

## Choosing the right source

| If you need… | Use |
| --- | --- |
| Headline TVL / volume to drop in a pitch deck | DefiLlama |
| ALB price for a watchlist | CoinGecko or DexScreener |
| Per-pair volume and trader counts | Dune (Sealaunch) |
| Holder distribution / concentration | Dune (Sealaunch) "Top 100 ALB + esALB" |
| esALB lock/unlock flow over time | Dune (Sealaunch) "ALB–esALB Lock/Unlock" |
| Cross-DEX benchmark (Alien Base vs. Aerodrome vs. Uniswap on Base) | Dune (Sealaunch) "DEX Activity Benchmark" |
| Live in-app exploration of a Base token | Explorer |
| Specific contract state (an `eth_call`) | Basescan or Blockscout |
| Governance proposal text and votes | Snapshot |
| Treasury composition right now | Safe (live) or Dune Fees panel (over time) |

## See also

- [ALB Token](alb-token.md) — for context on the supply numbers shown in the Dune dashboard.
- [Explorer](trading/epsilon-analytics.md) — the in-app data surface.
- [Audits & Security](audits-and-security.md) — what's verified vs. unverified.
- [Contracts](contracts.md) — addresses to plug into any explorer.
