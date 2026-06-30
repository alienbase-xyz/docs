---
description: Welcome to Alien Base
---

# Welcome to Alien Base

## What is Alien Base?

Alien Base is a meta-DEX native to the Base chain. It combines new and existing DeFi technologies in an accessible interface to give seasoned and new DeFi users the best tools available for **trading**, **providing liquidity**, and **launching new projects**.

What does that mean? We don't really know — ChatGPT wrote it. But in plain Earth-language: Alien Base is a very cool DEX and aggregator on Base with an excellent UI/UX, an ambitious roadmap, a capable team of Aliens, and one of the most active and engaged communities in the Base ecosystem.

## What can you do on Alien Base?

* **Trade any token on Base** — including tokens not on our token list — via Swaps, Limit Orders, Range Orders, Recurring (grid) Strategies, and DCA.
* **Provide liquidity** in V2 pools, Concentrated-Liquidity (V3) pools, or managed Vaults to earn fees and ALB rewards.
* **Lock $ALB into esALB** for governance, single-staking, and Real Yield in WETH from protocol fees.
* **Launch a token** with the Token Generator — Simple, Mintable, Burnable, Mint/Burn, or Tax templates, ready for trading on Alien Base or any other DEX.
* **Discover and analyze** every token, pool, and trade on Base via Epsilon Analytics — our chain-wide explorer.
* **Vote on protocol decisions** as an esALB holder via Snapshot.

## Quick Stats

| | |
| --- | --- |
| Token | $ALB ([0x1dd2…50c4](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4)) |
| Network | Base (chain id 8453) |
| Launch | August 8, 2023 |
| Lifetime swap volume | $2.86 B (V2 alone) |


For up-to-date market data, see our [Dune dashboard](https://dune.com/sealaunch/alienbase) (the canonical source, built with Sealaunch), [CoinGecko](https://www.coingecko.com/en/coins/alienbase), or [DefiLlama](https://defillama.com/protocol/alien-base-v3). For full contract addresses, see [Contracts](contracts.md). For the full data-source map, see [Data & Analytics](data-and-analytics.md).

## Where can I start?

1. **Track ALB and Alien Base** on [CoinGecko](https://www.coingecko.com/en/coins/alienbase), [CoinMarketCap](https://coinmarketcap.com/), [DexScreener](https://dexscreener.com/base/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4), and inside [Coinbase Wallet](https://www.coinbase.com/wallet). Add us to your watchlist.
2. **Join our community** — [Discord](https://discord.gg/alienbase) is the main hub. Real humans, real Aliens, lively debate on Alien Base, Base in general, memecoins, and beyond.
3. **Explore the dApp** at [app.alienbase.xyz](https://app.alienbase.xyz). If anything breaks, ping the team on Discord — someone will respond.
4. **Read these docs** — tutorials and reference material for every product.
5. **Follow us on socials** — [X / Twitter](https://twitter.com/AlienBaseDEX), [Medium](https://medium.com/@alienbase) for long-form articles, and [Reddit r/Alienbase](https://www.reddit.com/r/Alienbase).

## Quick Start (Q&A)

We know humans don't like to read. Maybe we Aliens can read your mind. Either way, here are the questions everybody asks.

### What can I do on Alien Base?

Trade, provide liquidity, lock ALB for governance + Real Yield, launch a token, and analyze the Base ecosystem. The bullets at the top of this page are the canonical list.

### Is Alien Base audited?

The contracts that Alien Base wrote from scratch are split between **audited / under review**, **audit upcoming**, and **inherited audits** from the upstream protocols we fork.

- **Epsilon** (the meta-aggregator + on-chain Epsilon Router) — **audited; report under review.** Will be published once the review cycle is complete.
- **Mothership** — audit upcoming. Pre-audit hardening visible in the public repo (fuzz tests, audit-scope commit from January 2026); the audit will run before the MVP is publicly accessible without supply caps.
- **All other native contracts** (V2 Factory/Router, BasedDistributorV2 farm, esALB / EsProxyMaster / EsTokenController, Token Generator, etc.) **rely on inherited audits** from the protocols they fork. Specifically:
  - **Uniswap V2 / V3 core** — audited by Trail of Bits, ABDK, and the Uniswap V3 Code4rena contest. Applies to the unchanged V2 + V3 cores.
  - **PancakeSwap MasterChef** — applies to the V2 farm contracts.
  - **Bunni / Timeless Finance** — applies to BunniHub and (mostly) BunniZap. Our BunniZap was lightly adapted.
  - **PancakeSwap SmartRouter** — applies to the V3 SmartRouter (lightly adapted).
  - **Bancor Carbon** — audited by PeckShield (May & July 2024) and ChainSecurity. Applies to the deployed CarbonController.
  - **Camelot xGRAIL escrow model** — the lineage of the esALB locking system.

Full breakdown with auditor names, dates, scopes, and report links: [Audits & Security](audits-and-security.md).

### What are the protocol fees?

| Product | Fee | Where it goes |
| --- | --- | --- |
| V2 swap | 0.30% (per pool, configurable) | LPs |
| V3 swap | 0.02% / 0.075% / 0.30% / 1% (per fee tier) | LPs (60%) + ALB & esALB stakers (40%) per AIP-2 |
| Epsilon front-end fee (non-native pools) | 0.03% (stables/ETH/BTC), 0.16% (everything else) | Treasury / esALB |
| Carbon orders (limit/range/recurring) | Maker-defined spread (0% if maker overlaps mid-price) | Maker keeps the spread; takers pay no Alien Base fee |
| DCA orders | 0.1% platform fee | Treasury |
| Token Generator | 0.015 ETH per token mint | Operating budget |

Full fee reference and historical changes: [Fees](fees.md). <!-- TODO:USER verify current swap fee numbers; PR #7 from community claimed 0.17% on the headline V2 fee -->

### What is esALB?

esALB ("escrowed ALB") is a non-transferable lock-wrapped form of ALB. You convert ALB → esALB 1:1 via the Lock UI on the [Dashboard](https://app.alienbase.xyz/dashboard). esALB is what earns governance voting power, single-staking APR (paid in ALB), and **Real Yield** (paid in WETH from protocol fees).

You can convert back at any time via two paths, mixable: 100% in 30 days (no penalty), or 1% every 12 hours (instant). [Full guide](escrowed-alb-esalb/README.md).

### How do I stake ALB?

1. Acquire ALB on the [Swap](https://app.alienbase.xyz/swap) page (any pair routed through Epsilon will give the best price).
2. Open the [Dashboard](https://app.alienbase.xyz/dashboard), find your ALB balance, click **Lock**.
3. Choose how much to lock and confirm. You receive non-transferable esALB.
4. Stake the esALB in the esALB single-stake vault on the [Vaults](https://app.alienbase.xyz/farms) page to begin earning rewards.

### Is the team doxxed?

Alien Base was founded and built by entrepreneurs and DeFi enthusiasts who chose to remain pseudonymous. There are no clear regulatory rules in many jurisdictions for DeFi projects: the rulebooks of classical or centralized finance don't translate cleanly (e.g., the entire concept of KYCing every user). Until that changes, we stay anonymous — even though the protocol is now governed by the DAO and not exclusively by the founding team. This lets us focus on building rather than litigating bureaucracy.

The team and its operating companies are doxxed to the **Base** and **Coinbase** teams and to multiple partners. The DAO Multisig signers, on the other hand, are public — see [DAO Multisig](alien-base-dao/dao-multisig.md).



### Where are the contracts?

Full canonical list in [Contracts](contracts.md). The headline ones:

- ALB token: [`0x1dd2…50c4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4)
- V2 Factory / Router / Farm: see [Contracts](contracts.md)
- V3 Factory / SmartRouter / NFTPositionManager / BunniHub: see [Contracts](contracts.md)
- esALB system (EsToken, EsProxyMaster, EsTokenController): see [Contracts](contracts.md)
- CarbonController (limit/range/recurring): [`0xe376…716e`](https://basescan.org/address/0xe3763886bf91d5466b416b37fdf2b6337897716e)
- Token Generator orchestrator: [`0xBcE7…d08d`](https://basescan.org/address/0xBcE75497D72b25c3509B62ae1a47CCfb502AD08d)
- DAO Multisig (5-of-8 Safe): [`0x4ab9…71e5`](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5)

Source code lives in [github.com/alienbase-xyz](https://github.com/alienbase-xyz/) — note that not every deployed contract has a public repo; we're working on improving this.

---

## Documentation map

- **[Get Started](#)** — bridging, wallets, and buying ALB
- **[Trading](trading-tools/epsilon.md)** — Swap, Epsilon, Limit/Range/Recurring/DCA orders
- **[Liquidity](alien-base-v3/README.md)** — Vaults, V3, Bunni, V2, Mothership
- **[ALB & esALB](alb-token.md)** — tokenomics, staking, vesting, Real Yield
- **[Governance](alien-base-dao/README.md)** — DAO, Foundation, Labs, AIP index
- **[Builders](tools-for-projects/token-generator/README.md)** — Token Generator and listing your project
- **[Reference](contracts.md)** — Contracts, Fees, Audits & Security, Glossary
- **[Roadmap](roadmap.md)** + **[Changelog](changelog.md)**
- **[Common Issues](common-issues/rpc-troubleshooting-guide.md)**
- **[Archive](#)** — deprecated products (Area 51, StableSwap, B3, Predictions, Lottery)

> *Last updated: {{today}}. Found something out of date? Open an issue on [github.com/alienbase-xyz/docs](https://github.com/alienbase-xyz/docs/issues) or ping the team on Discord.*
