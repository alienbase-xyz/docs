---
description: Alien Base's meta-aggregator and on-chain order engine
---

# Epsilon

**Epsilon** is Alien Base's trading engine. It has two halves:

1. The **meta-aggregator** — the aggregator of aggregators. Every swap quote scans all supported venues on Base and routes through whichever combination delivers the best execution.
2. The **Epsilon Router** — the on-chain contract where resting orders (Limit, Take Profit, Stop Loss, Trailing Stop, DCA) live, paired with the **Matcher** that executes them.

> _Last updated: July 6, 2026._

## The meta-aggregator

For each swap quote, Epsilon:

1. Pulls live quotes from every integrated DEX and aggregator on Base.
2. Considers single-hop, multi-hop, and split routes.
3. Subtracts the fee for each route (gas, pool fees, platform fee).
4. Returns the best net-of-fees price to the trader.

In nearly every case, the route Epsilon picks beats trading directly on any individual DEX — including Alien Base's own pools — because Epsilon can split a single trade across multiple pools to minimize price impact.

### Supported venues

DEX coverage (the venues whose pool liquidity Epsilon can route through):

| Venue                        | Type       |
| ---------------------------- | ---------- |
| Alien Base V2 / V3           | Native AMM |
| Uniswap                      | DEX        |
| Aerodrome                    | DEX        |
| PancakeSwap                  | DEX        |
| SushiSwap                    | DEX        |
| (Other DEXs via aggregators) |            |

Aggregator providers Epsilon can compare quotes against:

| Provider  | Type       |
| --------- | ---------- |
| OpenOcean | Aggregator |
| Odos      | Aggregator |
| 0x        | Aggregator |
| Bebop     | Aggregator |

Additional venues are added as Base's liquidity landscape evolves; the routing engine is configured server-side.

## The Epsilon Router

The Epsilon Router moves Epsilon's execution logic on-chain. Deployed at [`0x303ca5c65AabCb1CE242DF93F478c41E0E4D2580`](https://basescan.org/address/0x303ca5c65AabCb1CE242DF93F478c41E0E4D2580) (verified source on Basescan), it is the contract that holds and settles every resting order:

* [**Limit / Take Profit / Stop Loss / Stop Buy**](limit-orders.md) — fixed-price triggers, buy or sell side.
* [**Trailing Stop**](trailing-stop.md) — a stop level that follows the price up.
* [**DCA**](dca-orders.md) — time-sliced execution, with optional trigger price and stop-loss abort.

The Router has been **audited by** [**Hexens**](https://hexens.io/) (final report June 2026, before launch); the full report is published on [Audits & Security](../audits-and-security.md#epsilon-router--audited-by-hexens).

### The Matcher

Resting orders don't execute themselves. The **Matcher** is Epsilon's execution engine: it watches trigger conditions and, when one is met, fills the order through the meta-aggregator — the same best-route logic as a live swap. You pay gas only for approvals, while order creation is gasless. Execution gas is the Matcher's problem.

## Fees

Every trade Epsilon executes — swap or resting order — pays a platform fee tiered by asset class, plus the flat **0.05% Protocol execution fee**, on top of the underlying pool fees of whichever venues the route touches:

| Trade type                                           | Stables | Blue chips | Everything else |
| ---------------------------------------------------- | ------- | ---------- | --------------- |
| Swap                                                 | 0.01%   | 0.05%      | 0.15%           |
| Limit / Take Profit                                  | 0.01%   | 0.05%      | 0.10%           |
| Stop Loss / Stop Buy / Trailing Stop / DCA stop-loss | 0.10%   | 0.20%      | 0.45%           |
| DCA chunk                                            | 0.01%   | 0.10%      | 0.20%           |
| _+ Matcher execution fee (all of the above)_         | _0.05%_ | _0.05%_    | _0.05%_         |

Full breakdown: [Fees](../fees.md).

All Epsilon fees accrue to the protocol share — routed to the Treasury and the esALB Real Yield stream.

## Explorer (Epsilon Analytics)

Epsilon's data layer also powers the chain-wide **Explorer**. See [Explorer](epsilon-analytics.md).

## See also

* [Trading Terminal & Swap](swap.md)
* [Limit, Take Profit & Stop Loss](limit-orders.md) · [Trailing Stop](trailing-stop.md) · [DCA Orders](dca-orders.md)
* [Fees](../fees.md)
* [Audits & Security](../audits-and-security.md)
