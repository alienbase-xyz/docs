---
description: Alien Base's meta-aggregator routes every swap across Base for the best price
---

# Epsilon (meta-aggregator)

**Epsilon** is Alien Base's meta-aggregator — the aggregator of aggregators. Whenever you swap on Alien Base, Epsilon scans every supported venue on Base and routes through whichever combination delivers the best execution.

> *Last updated: {{today}}.*

## What Epsilon does

For each swap quote, Epsilon:

1. Pulls live quotes from every integrated DEX and aggregator on Base.
2. Considers single-hop, multi-hop, and split routes.
3. Subtracts the fee for each route (gas, pool fees, Epsilon front-end fee).
4. Returns the best net-of-fees price to the trader.

In nearly every case, the route Epsilon picks beats trading directly on any individual DEX — including Alien Base's own pools — because Epsilon can split a single trade across multiple pools to minimize price impact.

## Supported venues

DEX coverage (the venues whose pool liquidity Epsilon can route through):

| Venue | Type |
| --- | --- |
| Alien Base V2 / V3 | Native AMM |
| Uniswap | DEX |
| Aerodrome | DEX |
| PancakeSwap | DEX |
| SushiSwap | DEX |
| BaseSwap | DEX |
| Solidly | DEX |
| DackieSwap | DEX |
| SwapBased | DEX |

Aggregator providers Epsilon can compare quotes against (visible in the swap UI under "Route"):

| Provider | Type |
| --- | --- |
| OpenOcean | Aggregator |
| Odos | Aggregator |
| 0x | Aggregator |
| Bebop | Aggregator |

Additional venues are added as Base's liquidity landscape evolves; the routing engine is configured server-side.

## Front-end fee

Epsilon charges a small front-end fee for trades that route through **non-Alien-Base pools** or **non-Alien-Base tokens**. Native Alien Base trades (ALB pairs, V2/V3 native pools) pay only the standard pool fee — no Epsilon surcharge.

| Trade category | Front-end fee |
| --- | --- |
| Stablecoin / ETH / BTC pairs (non-native) | **0.03%** |
| All other tokens (non-native) | **0.20%** |

In practice this fee is much smaller than the savings from finding the best route. Full fee breakdown: [Fees](../fees.md).

## On-chain Epsilon Router

Historically Epsilon ran as off-chain routing logic, with the actual swap executed against the underlying pools by the user's wallet. The **Epsilon Router** moves this logic on-chain.

Status: **audited; report under review** as of {{today}}. Once the audit cycle is complete, the Router unlocks native order types that aren't possible without an on-chain aggregation layer:

- **Stop loss orders** — sell automatically if price falls below a level.
- **Trailing stop orders** — stop level that follows the price upward.
- **Stop-loss DCA** — DCA orders that abort if a stop is breached.
- **Conditional swaps** — execute one swap only if another condition is met.

These will surface in the Trading UI as the Router goes live.

## Epsilon Analytics

Epsilon's data layer also powers a chain-wide explorer. See [Epsilon Analytics](epsilon-analytics.md).

## How Epsilon makes money

Epsilon is a service Alien Base provides to users. The 0.03% / 0.20% front-end fee is the entirety of Epsilon's revenue. That fee accrues to the protocol share — routed to the Treasury and the esALB Real Yield stream.

## See also

- [Swap](swap.md)
- [Epsilon Analytics](epsilon-analytics.md)
- [Fees](../fees.md)
- [Audits & Security](../audits-and-security.md) — for the Epsilon audit status.
