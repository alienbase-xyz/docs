---
description: Escrowed ALB — what it is, what it does, and how to use it
---

# Escrowed ALB (esALB)

**esALB** is the locked, non-transferable form of ALB. It's the asset that earns governance voting power, single-staking APR, and **Real Yield** (WETH from protocol fees). If you plan to hold ALB long-term, you almost certainly want it as esALB.

> *Last updated: {{today}}.*

## In one paragraph

You convert ALB → esALB **1:1** via the Lock UI on the [Dashboard](https://app.alienbase.xyz/dashboard). esALB is non-transferable. You can stake esALB to earn unlocked ALB, vote on Snapshot, and receive Real Yield in WETH. To convert back, you use one of two paths (mixable): **100% in 30 days** with no penalty, or **1% every 12 hours** instantly. Both are documented below.

## At a glance

| | |
| --- | --- |
| esALB token | [`0x365c6d58…4113`](https://basescan.org/address/0x365c6d588e8611125de3bea5b9280c304fa54113) |
| Lock ratio | 1 ALB → 1 esALB (and back) |
| Transferable? | No. esALB is bound to the address that minted it. |
| Voting weight | 1× per esALB (10× per [govALB](#govalb-coming-via-aip-5) once AIP-5 ships) |
| Earn while staking? | Yes — unlocked ALB rewards from the esALB single-stake vault |
| Real Yield? | Yes — pro-rata share of WETH protocol fees |

## What esALB is for

- **Single-staking APR.** Stake esALB in the dedicated vault on the [Vaults](https://app.alienbase.xyz/farms) page to farm unlocked ALB.
- **Real Yield.** Stakers earn a share of protocol fees, paid in **WETH**, **USDC**, and other liquid assets — not in extra ALB inflation. Details: [Real Yield](real-yield.md).
- **Governance.** Voting power on Snapshot is weighted by esALB. See [Alien Base DAO](../alien-base-dao/README.md).
- **Airdrops & extra rewards.** Targeted distributions (partner tokens, special-event drops) generally land in esALB holders' wallets.

## How to lock ALB into esALB

1. Open the [Dashboard](https://app.alienbase.xyz/dashboard) and find your ALB balance in the portfolio panel on the right.
2. Click **Lock**. A modal opens.
3. Choose the amount of ALB to lock.
4. Approve the esALB contract to spend ALB (one-time, per address).
5. Confirm the conversion transaction.

You'll receive 1 esALB for every ALB locked. To see the esALB balance in your wallet, add the contract address [`0x365c6d58…4113`](https://basescan.org/address/0x365c6d588e8611125de3bea5b9280c304fa54113) as a custom token.

## Staking esALB

After locking, head to the [Vaults](https://app.alienbase.xyz/farms) page (formerly called "Farms"). The **esALB Single Stake** vault is at the top.

1. Click **Enable** to authorize the staking contract to move esALB.
2. Click **Stake** and choose the amount.
3. Rewards (unlocked ALB) accrue continuously. Click **Harvest** any time to claim.

Your staked esALB still counts for **governance voting** and **Real Yield**.

## How to unlock back to ALB

You can mix and match two redemption paths:

### Path A — 100% in 30 days, no penalty

1. On the Dashboard, find your locked esALB position. (If it's staked in the single-stake vault, unstake first.)
2. Click **Unlock** → choose **30 days**.
3. The esALB enters a "Vested" state for 30 days. While vesting, **you continue to earn rewards at a 30% reduction**.
4. After 30 days the **Redeem** button enables.

> {% hint style="warning" %}
> You have **7 days** to redeem after vesting completes. If you miss the window, the position re-locks and starts a new 30-day vesting cycle.
> {% endhint %}

### Path B — 1% every 12 hours, instant

1. On the Dashboard, click **Unlock** → choose **1% every 12 hours**.
2. Confirm the transaction. You instantly receive 1% of your esALB position back as ALB.
3. You can repeat every 12 hours. A countdown shows when the next claim is available.

The 1% is computed against your **total** esALB position, including any portion currently in 30-day vesting. You can use both paths simultaneously — e.g., put half into 30-day redemption and drip the rest 1% per 12h.

## Common pitfalls

- **"I don't see my locked esALB on the Dashboard."** It's probably staked in the esALB Single Stake vault. Unstake first; it'll reappear under your portfolio.
- **"My approve transaction succeeded but Lock still says I need to approve."** Likely an allowance-cap quirk on Base. See [Changing allowance](changing-allowance.md).
- **"I missed the 7-day redeem window."** It auto-relocks. Re-trigger redemption to start a fresh 30-day cycle, or use Path B to drip out.
- **"Why is my staking APR lower than expected?"** APR includes the unlocked ALB stream from the vault. The Real Yield (WETH) is shown separately. Total economics is APR + WETH yield + governance optionality.

## govALB (coming via AIP-5)

[AIP-5](https://medium.com/@alienbase/aip-5-building-alien-base-2-0-96dc24984cd2) introduces **govALB** — a longer-locked variant of esALB that confers **10× voting weight**. The trade-off is a longer effective lock (~2 years). It's designed for users who want maximum governance influence and are willing to commit time for it. Mechanics will be documented as it rolls out — see [Alien Base 2.0](../alien-base-2-0.md).

## Live data

The [Dune dashboard](https://dune.com/sealaunch/alienbase) tracks esALB live:

- **esALB Holders** — current count and growth over time.
- **ALB locked on esALB** and **ALB in esALB** — the supply view.
- **ALB-esALB Lock/Unlock** — daily inflows/outflows between ALB and esALB.
- **Total Holders (ALB + esALB)** — combined holder count, useful for evaluating decentralization.

## See also

- [esLP](eslp.md) — locked LP positions (e.g., ALB-ETH).
- [Vesting](vesting.md) — long-form vesting schedules (team, advisors, contributors).
- [Real Yield (WETH)](real-yield.md) — the protocol-fee distribution mechanism.
- [Changing allowance](changing-allowance.md) — fixing the "approve but won't lock" issue.
- [Data & Analytics](../data-and-analytics.md) — full data-source map.
- [Introducing EsALB: The Next Phase of Alien Base Tokenomics](https://medium.com/@alienbase/introducing-esalb-the-next-phase-of-alien-base-tokenomics-e5bfa049486f) — original launch article.
