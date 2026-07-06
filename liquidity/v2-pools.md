---
description: The original Alien Base AMM — Uniswap V2 fork
---

# V2 Pools (legacy)

V2 pools are the original Alien Base liquidity venue. Built on Uniswap V2 contracts, launched at TGE in **August 2023**. Despite the "legacy" label, V2 still hosts the most active ALB markets and remains a meaningful piece of the protocol.

> *Last updated: July 6, 2026.*

## When to use V2

- **Trading any pair you can't (or won't) actively manage.** V2 is constant-product (`x * y = k`) — no ranges, no concentrated liquidity, no out-of-range states.
- **Memecoins and small caps.** V2 is forgiving of price discovery and has the simplest LP UX.
- **ALB markets.** ALB-WETH and other ALB pairs primarily trade in V2 — see the [ALB liquidity section](../alb-token.md#alb-liquidity).
- **Set-and-forget LPing.** No active management, no rebalance, no out-of-range risk.

## Mechanics

- **50/50 deposit.** You provide both tokens in equal value at the current price.
- **Full-range exposure.** Your liquidity is active across every price point, from zero to infinity.
- **Pool fee.** **0.16%** per swap, paid by the taker and distributed to LPs. The V2 Factory's `feeToSetter` is the DAO Multisig — the protocol-side carve-out can be enabled by DAO vote.
- **LP token.** Standard ERC-20. Stakeable, transferable, farmable.

## Where to find them

- **Trade.** The [trading terminal](https://app.alienbase.xyz/swap) routes through V2 automatically when it's the best venue.
- **LP.** **New position** (on the [Vaults](https://app.alienbase.xyz/vaults) or Dashboard page) → select **V2** — add or remove V2 liquidity directly.
- **Farm.** The old V2 farms live under **Vaults → Legacy farms**; their emissions have wound down under AIP-5, so the tab is mainly for unstaking. See [Vaults](vaults.md#legacy-farms-tab).

## ALB-WETH — the headline pair

The deepest ALB market on Alien Base is the V2 ALB-WETH pool: [`0xbcd27A43…6fcB`](https://basescan.org/address/0xbcd27A437eBe92555Cee6b5bBeDdAC639a1b6fcB). LPing here is also the basis for the **esLP ALB-ETH** locking position (see [esLP](../escrowed-alb-esalb/eslp.md)).

## Why "legacy"?

V2 isn't going anywhere — it's a robust, battle-tested AMM. We tag it "legacy" because:

- New deep-liquidity markets (stablecoin pairs, blue chips) launched on V3 prefer the higher capital efficiency.
- ALB emission programs are increasingly directed toward V3 / Bunni Vaults and (under [AIP-5](../alien-base-2-0.md)) toward the POL Fund.
- Most user-facing UI surfaces emphasize Vaults / V3.

But V2 remains the right answer for many use cases — especially for new tokens, memecoins, and any pair where active management isn't worth the overhead.

## See also

- [Concentrated Liquidity (V3)](v3.md) — the higher-efficiency alternative.
- [Vaults overview](vaults.md)
- [Token Generator](../tools-for-projects/token-generator/README.md) — the easiest path from "I have an idea" to "my token has a V2 pool".
- [Contracts](../contracts.md) — V2 Factory, Router, Farm addresses.
