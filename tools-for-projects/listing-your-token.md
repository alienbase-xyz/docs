---
description: Get your token visible on the data sites and wallets that matter
---

# Listing your token

Once your token has at least one trade and a liquidity pool, it's discoverable on Base — but it'll show up as a generic "unverified" entry until you fill in the metadata. This page is a checklist for getting your token properly listed across the sites traders actually use.

> *Last updated: July 6, 2026.*

## Prerequisites

Before any of the steps below:

- Token is deployed and verified on Basescan (the [Token Generator](token-generator/README.md) does this automatically).
- At least one liquidity pool exists (typically a V2 pool with WETH; see [V2 Pools](../liquidity/v2-pools.md)).
- At least one trade has happened on that pool.

## Basescan (the source of truth)

Most other sites pull from Basescan, so this is the most important step.

1. Open your token page on [Basescan](https://basescan.org/).
2. Sign in with the **owner wallet** (the address that deployed the token).
3. Click **Update** and fill in:
   - Logo (square, ≥256×256 PNG)
   - Website
   - X / Twitter
   - Telegram, Discord, Medium, etc. (whatever applies)
   - Description

Once approved, the metadata propagates to many other tools — DexScreener, GeckoTerminal, MetaMask, etc.

## DexScreener

[DexScreener](https://dexscreener.com/) picks up tokens automatically once they have a trade. To add the logo and socials directly (rather than waiting for Basescan to propagate), use the [token info marketplace](https://marketplace.dexscreener.com/product/token-info). Standard listing fee: $300. Tokens deployed via the Alien Base Token Generator can qualify for a discount — <!-- TODO:USER confirm current discount terms / partnership status -->.

## GeckoTerminal

[GeckoTerminal](https://www.geckoterminal.com/) auto-indexes after the first trade. To add logo / socials, click **Update Token Info** on your token page. Free.

## DexTools

[DexTools](https://www.dextools.io/app/en/base/pairs) auto-indexes. Click **Update Token Info** on your token page. Free, with optional paid promotion.

## CoinGecko

CoinGecko requires manual submission via [this form](https://www.coingecko.com/en/coins/new). Listing has minimum requirements (typically liquidity, age, holders, trading volume). It can take weeks to be reviewed.

## CoinMarketCap

CoinMarketCap is the slowest and strictest of the major listing sites. Submit via [this form](https://coinmarketcap.com/request). For most projects, the realistic path is the **$5,000 priority** option — without it, organic listings are heavily backlogged.

## Wallet integrations

- **MetaMask / Coinbase Wallet** automatically display the Basescan logo if it's set.
- For some wallets, getting on the **token list** (a curated registry like Coinbase's Base list) requires direct submission. See each wallet's developer docs.

## Trust signals to set up alongside listings

Listings make you visible. Trust signals make people trade. The high-impact ones:

- **Lock or burn LP.** Lock via Gempad, Team Finance, etc., or hard-burn by sending LP to `0x000000000000000000000000000000000000dEaD`.
- **Renounce ownership** if your token is Mintable or Tax. (Don't renounce if you actually need to keep tweaking parameters — this is a one-way action.)
- **Verify your contract** on Basescan. (Token Generator does this automatically.)
- **Public socials** with consistent branding across X, Telegram, Discord, the project website, and Basescan metadata.
- **A clear post on Discord / X** announcing the launch with the contract address. Pre-empts impostors.

## Fast-path for Token-Generator-deployed tokens

If you deployed via the [Token Generator](token-generator/README.md):

1. Token is already verified — skip the manual verification dance.
2. Add liquidity via **New position** on [app.alienbase.xyz/vaults](https://app.alienbase.xyz/vaults).
3. Update Basescan info while waiting for the first organic trade.
4. Apply to DexScreener / DexTools / GeckoTerminal in parallel.
5. Apply to CoinGecko after a few days of organic volume.
6. Apply to CMC last (it's the slowest).

## See also

- [Token Generator](token-generator/README.md)
- [Token Generator FAQ](token-generator/faq.md)
- [V2 Pools](../liquidity/v2-pools.md) — for adding the initial liquidity.
