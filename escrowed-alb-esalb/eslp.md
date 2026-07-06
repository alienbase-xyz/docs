---
description: Escrowed LP positions — locked liquidity that earns boosted yield
---

# esLP

**esLP** ("escrowed LP") applies the esALB locking pattern to liquidity-pool tokens. The flagship esLP position is **esLP ALB-ETH** — a locked V2 LP token that earns boosted ALB rewards and protocol-fee yield, while remaining non-transferable.

> *Last updated: July 6, 2026.* esLP was introduced after esALB shipped (April 2024) and is referenced in the [Welcome page](../README.md) and the AIP-2 fee-split structure.

## What esLP is

A non-transferable, lock-wrapped version of an LP token (currently ALB-ETH V2). The pattern is identical to esALB:

- Lock LP → esLP **1:1**.
- esLP earns higher emissions than the unlocked LP farm.
- esLP also receives a share of the **Real Yield** stream (WETH from protocol fees).
- Unlock paths mirror esALB: 100% after a 30-day cooldown (no penalty) or 1% instantly every 24 hours.

## Why use esLP

If you're providing the ALB-ETH liquidity that powers Alien Base's core market, esLP rewards you for committing to that role. It compresses the gap between "passive LP" and "long-term aligned holder" by giving committed LPs:

- A boost on top of the regular farm APR.
- A direct share of WETH Real Yield (the same stream that pays esALB stakers).
- Voting power on Snapshot proposals (esLP counts toward the esALB-equivalent voting strategy at a configured weight).

## How to lock

> {% hint style="info" %}
> The exact UI flow for esLP varies depending on whether the position lives in the legacy Farms tab or the new [Vaults](https://app.alienbase.xyz/vaults) page. Steps below describe the current Vaults flow.
> {% endhint %}

1. Provide ALB-ETH liquidity on the [V2 pool](https://app.alienbase.xyz/swap) and receive your LP token.
2. Open the [Vaults](https://app.alienbase.xyz/vaults) page and find the **esLP ALB-ETH** vault.
3. Click **Lock** → choose the LP amount → approve the contract → confirm.
4. The LP token disappears from your wallet; an equivalent esLP balance appears in your portfolio.

To stake the esLP for boosted rewards, find the corresponding stake card in the same Vaults page, click **Stake**, and confirm.

## Unlocking

Same two paths as esALB:

- **100% in 30 days, no penalty.** The position enters a 30-day vesting state. You still farm at a 30% reduction during this window, then redeem within 7 days after the vest completes (or it re-locks).
- **1% every 24 hours, instant.** In the unstake modal, toggle "Instant 1% Redemption" → confirm.

You can mix the two paths as needed.

## Contracts

The esLP contracts on Base: `esLP-ALB-ETH` ("Infinite") at [`0x3d3a5ad6…8ea0`](https://basescan.org/address/0x3d3a5ad6d7beab234d7f0338a01e62b1d36d8ea0) and `esLP-B-ALB-ETH` ("Backstop") at [`0x4a023efe…6978`](https://basescan.org/address/0x4a023efe4b5cd304e800f29074186164fda36978). Both appear under **Vaults → Locked earn** in the dApp. ALB-WETH is currently the only pair with esLP positions.

<!-- TODO:USER (hidden): confirm the live esLP boost (e.g., "esLP ALB-ETH receives X% more emissions vs. the unlocked LP farm"). -->

## See also

- [Escrowed ALB (esALB)](README.md) — the underlying locking primitive.
- [Real Yield (WETH)](real-yield.md) — the protocol-fee distribution that esLP shares in.
- [V2 Pools (legacy)](../liquidity/v2-pools.md) — where the underlying LP token comes from.
