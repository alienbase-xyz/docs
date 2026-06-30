---
description: Escrowed LP positions — locked liquidity that earns boosted yield
---

# esLP

**esLP** ("escrowed LP") applies the esALB locking pattern to liquidity-pool tokens. The flagship esLP position is **esLP ALB-ETH** — a locked V2 LP token that earns boosted ALB rewards and protocol-fee yield, while remaining non-transferable.

> *Last updated: {{today}}.* esLP was introduced after esALB shipped (April 2024) and is referenced in the [Welcome page](../README.md) and the AIP-2 fee-split structure.

## What esLP is

A non-transferable, lock-wrapped version of an LP token (currently ALB-ETH V2). The pattern is identical to esALB:

- Lock LP → esLP **1:1**.
- esLP earns higher emissions than the unlocked LP farm.
- esLP also receives a share of the **Real Yield** stream (WETH from protocol fees).
- Unlock paths mirror esALB: 100% in 30 days (no penalty) or 1% every 12 hours.

## Why use esLP

If you're providing the ALB-ETH liquidity that powers Alien Base's core market, esLP rewards you for committing to that role. It compresses the gap between "passive LP" and "long-term aligned holder" by giving committed LPs:

- A boost on top of the regular farm APR.
- A direct share of WETH Real Yield (the same stream that pays esALB stakers).
- Voting power on Snapshot proposals (esLP counts toward the esALB-equivalent voting strategy at a configured weight).

## How to lock

> {% hint style="info" %}
> The exact UI flow for esLP varies depending on whether the position lives in the legacy Farms tab or the new [Vaults](https://app.alienbase.xyz/farms) page. Steps below describe the current Vaults flow.
> {% endhint %}

1. Provide ALB-ETH liquidity on the [V2 pool](https://app.alienbase.xyz/swap) and receive your LP token.
2. Open the [Vaults](https://app.alienbase.xyz/farms) page and find the **esLP ALB-ETH** vault.
3. Click **Lock** → choose the LP amount → approve the contract → confirm.
4. The LP token disappears from your wallet; an equivalent esLP balance appears in your portfolio.

To stake the esLP for boosted rewards, find the corresponding stake card in the same Vaults page, click **Stake**, and confirm.

## Unlocking

Same two paths as esALB:

- **100% in 30 days, no penalty.** The position enters a 30-day vesting state. You still farm at a 30% reduction during this window, then redeem within 7 days after the vest completes (or it re-locks).
- **1% every 12 hours, instant.** Click "Unlock" → "1% every 12 hours" → confirm.

You can mix the two paths as needed.

## Open items

- <!-- TODO:USER -->Confirm the current esLP token contract address on Base — the EsToken family is at [`0x365c6d58…4113`](https://basescan.org/address/0x365c6d588e8611125de3bea5b9280c304fa54113) (the esALB token); we need the esLP ALB-ETH contract specifically.
- <!-- TODO:USER -->Confirm the live esLP boost (e.g., "esLP ALB-ETH receives X% more emissions vs. the unlocked LP farm").
- <!-- TODO:USER -->Confirm whether other esLP positions (e.g., ALB-USDC, ALB-cbBTC) currently exist or are planned post-AIP-5 POL deployment.

## See also

- [Escrowed ALB (esALB)](README.md) — the underlying locking primitive.
- [Real Yield (WETH)](real-yield.md) — the protocol-fee distribution that esLP shares in.
- [V2 Pools (legacy)](../liquidity/v2-pools.md) — where the underlying LP token comes from.
