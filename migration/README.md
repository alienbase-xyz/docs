---
description: How to move your old ALB and esALB to the new Alien Base 2.0 contracts, 1:1
---

# ALB Migration Guide

As part of [Alien Base 2.0 (AIP-5)](../alien-base-2-0.md), ALB and esALB moved to **new token contracts on Base**. Holders swap their old tokens for new ones **1:1** through the on-chain Migration Contract. There is **no deadline** and nothing happens to your tokens if you wait, but only the new tokens are supported going forward.

> _Last updated: October 22, 2026._ Migrate at [app.alienbase.xyz/migration](https://app.alienbase.xyz/migration).

## TL;DR

* **Old ALB → new ALB, 1:1.** Same name, same symbol, new contract.
* **Old esALB → new esALB, 1:1.** Your new esALB is earning from the moment it lands in your wallet; there is no separate staking step.
* **No deadline, no fee** (beyond Base gas). You can migrate any time, in as many batches as you like, including old ALB you buy later.
* **Old tokens you migrate are locked in the Migration Contract forever.** It has no withdraw function and no owner.
* **Only use [app.alienbase.xyz/migration](https://app.alienbase.xyz/migration)** or the verified contract below. Alien Base will never DM you a migration link or ask for your seed phrase.

## Addresses

| Token / contract       | Old (legacy)                                                                                                            | New                                                                                                                     |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **ALB**                | [`0x1dd2d631c92b1aCdFCDd51A0F7145A50130050C4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) | [`0x1b23704e3f4bc7081fb00cec582183e3fe43cef7`](https://basescan.org/token/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7) |
| **esALB**              | [`0x365c6d588e8611125De3bEA5B9280C304FA54113`](https://basescan.org/token/0x365c6d588e8611125de3bea5b9280c304fa54113) | [`0x32d9f29170a023794025375df6949f56844e4473`](https://basescan.org/token/0x32d9f29170a023794025375df6949f56844e4473) |
| **govALB**             | —                                                                                                                       | [`0x7fdb2cbe3dd946b6b4521d4a2cce62296ec1441d`](https://basescan.org/token/0x7fdb2cbe3dd946b6b4521d4a2cce62296ec1441d) |
| **Migration Contract** | —                                                                                                                       | [`0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d`](https://basescan.org/address/0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d) |

All new tokens use 18 decimals. To see them in your wallet, add the new addresses as custom tokens. The full list of Alien Base 2.0 contracts is on the [Contracts](../contracts.md#new-token-system-aip-5) page.

## Why a new contract?

AIP-5 rewrote ALB's tokenomics: Protocol-Owned Liquidity instead of farming, a Dev Line of Credit, govALB, flexible emissions, and a one-time supply cap raise to **1,051,000,000 ALB**. The old token and the old esALB/farming stack couldn't support those mechanics cleanly, so the DAO moved to a fresh set of contracts instead of patching the old ones. See [Alien Base 2.0](../alien-base-2-0.md) for the full rationale.

## Before you start

* **Network:** Base. Keep a little ETH on Base for gas. Each step is one or two transactions (an approval, then the action).
* **Wallet:** connect the wallet that holds your old ALB / esALB. If you hold tokens in several wallets, migrate each wallet separately.
* **Old esALB in the middle of a 30-day redemption** can't be migrated as-is. Either wait until the redemption completes and claim it as old ALB (then migrate that ALB), or cancel the redemption to get the esALB back, then migrate it. Cancelling forfeits the vesting progress of that redemption.
* **Liquidity positions** that contain old ALB (V2/V3 LPs, Bunni vaults, esLP) are not migrated by this page. Withdraw the position first, then migrate the ALB you receive. See [FAQ](faq.md#what-about-my-lp-positions-and-vaults).

## Step by step

Open [app.alienbase.xyz/migration](https://app.alienbase.xyz/migration) and connect your wallet. The page reads your balances and shows:

* **Old ALB in wallet**
* **Old esALB staked** (allocated to the old esALB staking vault)
* **Old esALB in wallet**
* **Pending ALB rewards** from the old esALB vault

It then builds a checklist with only the steps you need. If you hold no esALB, you'll only see step 3.

### Step 1: Unstake old esALB

If your old esALB is staked in the old **Locked earn** vault, click **Unstake esALB**. This pulls it back into your wallet so it can be migrated.

Unstaking also **pays out your pending old-ALB rewards** to your wallet. Those rewards are then picked up in step 3, so you don't lose them.

### Step 2: Migrate esALB

Click **Migrate esALB**. You'll approve the Migration Contract to move your old esALB (once), then confirm the migration.

What happens on-chain:

1. Your old esALB is transferred into the Migration Contract and locked there permanently.
2. The contract mints the same amount of new ALB and deposits it into the new esALB contract on your behalf.
3. You receive **new esALB 1:1**, fully backed by new ALB. It starts earning immediately (see [esALB](../escrowed-alb-esalb/)).

### Step 3: Migrate ALB

Click **Migrate ALB**. Approve once, then confirm. Your old ALB, including any rewards paid out in step 1, is locked in the Migration Contract and you receive **new ALB 1:1**.

### Done

When nothing old is left in your wallet, the page shows **Nothing to migrate**. Check your wallet for the new ALB / esALB (add the [new addresses](#addresses) as custom tokens if they don't show up).

You can come back any time. If you receive more old ALB later (for example from an LP withdrawal or a purchase), the same steps work again.

## Migrating without the app

The Migration Contract is verified, so you can also use it directly from the **Write Contract** tab on Basescan:

1. On the old token (ALB or esALB), call `approve(0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d, amount)`.
2. On the [Migration Contract](https://basescan.org/address/0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d#writeContract), call `migrateALB(amount)` or `migrateEsALB(amount)`. Amounts are in wei (18 decimals).

Old esALB must be in your wallet (not staked) before `migrateEsALB` will succeed.

## How the Migration Contract works

The contract is intentionally small. It has two functions and no admin controls:

| Function               | What it does                                                                                                   |
| ---------------------- | -------------------------------------------------------------------------------------------------------------- |
| `migrateALB(amount)`   | Pulls `amount` old ALB from you, keeps it, mints `amount` new ALB to you.                                     |
| `migrateEsALB(amount)` | Pulls `amount` old esALB from you, keeps it, mints `amount` new ALB and deposits it as new esALB for you.     |

* There is **no owner, no pause, and no withdraw**. Old tokens sent in can never leave.
* Running totals are public: `totalLegacyALBLocked()` and `totalLegacyEsALBLocked()` on the contract.
* New ALB can only be minted by authorised minters (the Migration Contract and the new farm Distributor), and never above the hard-coded **1,051,000,000** cap. See [ALB Token](../alb-token.md#supply).

## Need help?

* Read the [Migration FAQ](faq.md).
* Ask in [Discord](https://discord.gg/alienbase). The team will never DM you first.
* For failed or stuck transactions, see [Pending or failed transactions](../common-issues/pending-or-failed-transactions.md).
