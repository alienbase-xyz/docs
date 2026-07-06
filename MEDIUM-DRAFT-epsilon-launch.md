# MEDIUM DRAFT — delete this file after publishing

> Suggested title options:
>
> 1. **Epsilon Evolved: Stop Losses, Trailing Stops and On-Chain Orders Land on Base**
> 2. Introducing the Epsilon Router: CEX-Grade Orders, Fully On-Chain
> 3. The Best Aggregator on Base Just Learned New Tricks
>
> Suggested images: hero shot of the new trading terminal (use `/.gitbook/assets/01-trade-terminal.png`), the trailing stop form (`05-trailing-stop.png`), an open order resting on the chart (`17-open-orders.png`).

---

# Epsilon Evolved: Stop Losses, Trailing Stops and On-Chain Orders Land on Base

Today we're shipping the biggest upgrade to Alien Base since we launched in August 2023: a full **trading terminal** at [app.alienbase.xyz](https://app.alienbase.xyz), powered by the new **Epsilon Router** — our own custom-built, audited, on-chain order engine.

The short version: Alien Base is now the only place on Base where you can set a **Stop Loss**, a **Trailing Stop**, or a **DCA with a trigger price and downside protection** — all executing on-chain, non-custodially, at the best price available anywhere on the chain.

The long version is below. Grab a beverage, human.

## What is Epsilon?

Epsilon is Alien Base's trading engine — the aggregator of aggregators. Every time you swap on Alien Base, Epsilon scans **every meaningful liquidity venue on Base** — Uniswap, Aerodrome, PancakeSwap, SushiSwap, BaseSwap and more, plus aggregator partners like OpenOcean, Odos, 0x and Bebop — and routes your trade through whichever combination of pools delivers the best net price. It can split a single trade across multiple venues to minimize price impact, and in nearly every case the result beats trading on any single DEX directly — including our own pools.

That has been our philosophy from day one: why should an exchange limit itself to its own liquidity? You should be able to trade **any token on Base, the moment it launches**, from one interface, at the best price on the chain. Epsilon is how we do that.

## From APIs to our own contracts

Here's the honest history. When Epsilon first launched, it aggregated liquidity **through third-party APIs**. We integrated OpenOcean, then ParaSwap, then Odos, and compared their quotes to route your trade. It worked — it made Alien Base the best-priced venue on Base — but it had a ceiling:

- **We didn't control execution.** Routing logic lived in someone else's infrastructure.
- **We couldn't build new order types.** An API that quotes swaps can't hold a resting stop loss for you.
- **Every feature was a negotiation.** Our roadmap was rate-limited by our partners' roadmaps.

So we made the call that defines this upgrade: **we built our own contracts.** The Epsilon Router is a from-scratch, on-chain order engine — designed, built, and battle-tested by Alien Labs, and **audited by [Hexens](https://hexens.io/)** (final report June 2026, before a single user order touched production; the full report is published in [our docs](https://docs.alienbase.xyz/audits-and-security)).

The meta-aggregation is still there — better than ever — but execution now runs through our own audited infrastructure. That's what unlocked everything below.

## What's new

### A real trading terminal

The swap page is now a full terminal: a TradingView chart with indicators and drawing tools, chain-wide token search with safety data inline, a positions panel tracking your balances, average entry price and unrealized P&L, your open orders drawn directly on the chart, and a trending ticker for the most active tokens on Base. It looks like a CEX. It settles like a DEX.

### Limit orders, Take Profit, Stop Loss, Stop Buy

Set a price; the order rests **on-chain** in the Epsilon Router until it triggers. Buy the dip at your price, sell into strength at your target, or — for the first time on Base — **cut a loss automatically** while you sleep. Orders are non-custodial, cancellable anytime, and every fill routes through the meta-aggregator for the best price at execution.

### Trailing Stop

The "let winners run, lock in gains" order — previously a CEX-only luxury. Set a trail percentage (say, 10%) and the stop level follows the price up as it climbs. It never moves down. When the price retraces by your trail amount from its peak, Epsilon sells. Ride the trend; keep the gains.

### DCA, upgraded

Dollar-cost averaging was already on Alien Base — but the new DCA is a different species:

- **Trigger price** — the DCA stays dormant until the market reaches your level, then starts executing. "Buy the breakout, slowly."
- **Stop-loss protection** — if the price collapses mid-run, the remaining schedule aborts and your unspent balance is released. No more averaging into a falling knife.

Each chunk executes at the best available route at that moment, on schedule, fully on-chain.

### The Matcher

Resting orders don't execute themselves. The **Matcher** — Epsilon's execution engine — watches every trigger condition and fills orders through the meta-aggregator the moment they're ready. You pay gas only when you create or cancel an order; execution gas is the Matcher's problem, not yours.

## Why this matters

Every other "limit order" experience on Base is either a market order in a trench coat, a custodial workaround, or absent entirely. With the Epsilon Router, Alien Base is — as of today — **the best aggregator on Base and the only venue with true on-chain stop losses and advanced order types.**

And because it's ours, the order-type roadmap is now limited by our imagination, not by an API contract.

## What's next

Two big things are already in motion:

- **The Alien Base 2.0 migration (AIP-5).** The DAO approved the biggest tokenomics overhaul in our history: farming gives way to a Protocol-Owned-Liquidity fund with buyback-and-burn, fixed halvings give way to revenue-linked emissions, govALB brings 10× voting power for long-horizon holders, and the dev budget becomes a tracked Line of Credit that pays interest back to esALB holders. The on-chain rollout is executing now.
- **Mothership alpha.** Our first fully original protocol: an Automated Liquidity Manager that runs multi-range, actively rebalanced V3 strategies for you. The audit is in flight, and the gated alpha — with strict supply caps while it earns trust — opens right after. LPs, your set-and-forget era is coming.

The invasion continues. 👽

---

**Try it:** [app.alienbase.xyz](https://app.alienbase.xyz)
**Read the docs:** [docs.alienbase.xyz](https://docs.alienbase.xyz)
**Audit report:** [Audits & Security](https://docs.alienbase.xyz/audits-and-security)
**Join us:** [Discord](https://discord.gg/alienbase) · [X / Twitter](https://twitter.com/AlienBaseDEX)
