---
description: Common questions about the ALB / esALB migration to the Alien Base 2.0 contracts
---

# Migration FAQ

> _Last updated: October 22, 2026._ New to the migration? Start with the [Migration Guide](README.md).

## The basics

### Do I have to migrate?

Only if you want to keep using ALB inside Alien Base. The old tokens keep working as ERC-20s, but new features, rewards, Real Yield, govALB and future governance are built on the new contracts. Old ALB and esALB are **no longer actively supported**.

### Is there a deadline?

No. The Migration Contract has no end date, no owner and no pause switch. You can migrate today, next month or next year, and in as many batches as you like.

### What's the ratio?

**1:1** for both swaps. 1 old ALB → 1 new ALB. 1 old esALB → 1 new esALB.

### Does it cost anything?

No fee. You only pay Base gas for the approval and migration transactions, typically a few cents.

### What happens to my old tokens?

They are transferred into the [Migration Contract](https://basescan.org/address/0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d) and stay there permanently. The contract has no function that can move them out, so migrated old tokens are effectively retired from circulation.

### Can I migrate back?

No. Migration is one-way.

### I bought old ALB after the migration started. Can I still migrate it?

Yes. Any old ALB can be migrated at any time, no matter when or how you got it.

## esALB and staking

### My old esALB was staked. Do I lose my rewards?

No. The first step on the migration page unstakes your old esALB, which also pays out your pending old-ALB rewards to your wallet. The final step migrates that ALB together with the rest.

### Do I need to stake my new esALB?

No. New esALB earns **just by sitting in your wallet**: the esALB contract reports every balance change to the new staking contract, so rewards (ALB and WETH) start accruing the moment you receive it. See [esALB](../escrowed-alb-esalb/).

### My old esALB is in the middle of a 30-day redemption. What do I do?

That esALB is held by the old contract, so the migration page can't move it. You have two options:

1. **Wait** for the redemption to finish, claim it as old ALB, then migrate that ALB. You keep the vesting progress.
2. **Cancel** the redemption on the old esALB, then migrate the esALB you get back. You lose that redemption's progress.

### Are the new esALB rules the same as the old ones?

No, they changed with AIP-5. New esALB has a **30 to 60 day** exit: redeem after 30 days at 85%, rising linearly to 100% at 60 days, with 70% of your position still earning while it vests. There's also a small **instant redemption allowance** of 2% of your position every 48 hours. Full details on the [esALB](../escrowed-alb-esalb/#redeeming-esalb-back-to-alb) page.

### What about govALB?

govALB is new with AIP-5. You get it by converting new esALB 1:1. It's a 2-year lock with **10× voting power** and the same earning rate as esALB. There is no old govALB to migrate. See [govALB](../escrowed-alb-esalb/#govalb).

## Liquidity, farms and vaults

### What about my LP positions and vaults?

LP tokens, V3 positions, Bunni vaults and esLP positions that contain old ALB are **not** migrated automatically. To move them:

1. Withdraw (or unstake and withdraw) the position in the app.
2. Migrate the old ALB you receive on the [migration page](https://app.alienbase.xyz/migration).
3. If you want to keep providing liquidity, add the new ALB to a new-ALB pool or vault.

esLP positions are **withdrawable immediately**, with no unlock period, so step 1 is instant for them. See [esLP](../escrowed-alb-esalb/eslp.md).

### Are the old farms still running?

AIP-5 replaces farming with Protocol-Owned Liquidity. Old farms are being wound down and new incentives run through the new Distributor contract. Rewards already earned in old farms remain claimable; anything paid out in old ALB can be migrated.

## Trading and listings

### Which ALB should I buy?

The **new ALB** ([`0x1b23…cef7`](https://basescan.org/token/0x1b23704e3f4bc7081fb00cec582183e3fe43cef7)) is the canonical token from now on. Old ALB can still be bought and migrated 1:1, so if you see a better price on old ALB you can buy it and migrate. Always check the contract address before swapping. See [Buying ALB](../get-started/buying-alb.md).

### Will CoinGecko, CoinMarketCap and DexScreener show the new token?

The listings on the major trackers are being moved to the new contract. Until each one updates, it may still show the old token's price and supply. The contract addresses on this page are the source of truth.

### What's the new total and circulating supply?

The new ALB has a hard cap of **1,051,000,000**. Total supply only grows as people migrate and as new emissions are minted. **Circulating supply** = total supply − ALB backing new esALB − ALB backing govALB − ALB held by the DAO Multisig. Live figures are on the [ALB Token](../alb-token.md#supply) page and the public supply API.

## Safety

### How do I avoid scams?

* Only migrate at **app.alienbase.xyz/migration** or directly on the verified [Migration Contract](https://basescan.org/address/0xa53d1fd0aae780f5f4f3c2f75a35ca9e74269d3d#writeContract).
* The only approval the migration needs is for **old ALB or old esALB** to the Migration Contract `0xa53d…9d3d`. If a site asks you to approve anything else, stop.
* Alien Base will never DM you, never ask for your seed phrase, and never ask you to send tokens to an address to "migrate" them.

### Is the new code audited?

The Alien Base 2.0 contracts went through an audit review round before deployment, and its fixes are in the deployed code. The report will be published on the Audits page. All new contracts are verified on-chain, and the Migration Contract itself is two short functions with no admin controls. See [Audits & Security](../audits-and-security.md#new-token-system-aip-5).

### Who controls the new contracts?

The new ALB, esALB, govALB, staking and Distributor contracts are owned by the 7-day [TimelockController](https://basescan.org/address/0x1c7e4284423c1a2362c49b1ea223b73e38c81e21), so any admin change is public for 7 days before it can execute. The Migration Contract has no owner at all. Details on [Audits & Security](../audits-and-security.md#onchain-control-surface).

## Something went wrong

### My migration transaction failed

* **"Approve" succeeded but the migration reverts:** wait a few seconds for the approval to confirm and retry. The app re-reads your allowance before each step.
* **esALB step says "Unstake first":** your old esALB is still staked. Run step 1.
* **I don't see the new tokens:** add the new [addresses](README.md#addresses) as custom tokens in your wallet.
* Still stuck? See [Pending or failed transactions](../common-issues/pending-or-failed-transactions.md) or ask in [Discord](https://discord.gg/alienbase).
