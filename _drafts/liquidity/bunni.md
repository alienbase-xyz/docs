---
description: Why Alien Base wraps V3 positions as ERC-20 share tokens
---

# Bunni explainer

**Bunni** is a Uniswap V3 wrapper developed by [Timeless Finance](https://timelessfi.com/). It turns each V3 LP position from an NFT into an **ERC-20 share token** — making concentrated-liquidity positions composable, transferable, and farmable.

> *Last updated: {{today}}.* Alien Base ships a fork of Bunni alongside its V3 stack.

## Why wrap V3 positions

Native Uniswap V3 represents each LP position as an **ERC-721 NFT**. That's expressive (every position is unique) but it's a pain to compose with the rest of DeFi:

- Most farming contracts expect ERC-20 tokens, not NFTs.
- NFTs don't aggregate cleanly — you can't "pool" 100 different NFTs together.
- Per-user NFT positions mean the protocol can't farm on behalf of users, only on per-NFT bases.

Bunni solves this by deploying a single **Vault** per `(token0, token1, fee tier, range)` tuple. When you deposit into the Vault, the Vault holds the NFT and gives you an ERC-20 share token in return. Now:

- Many users share the same NFT, pooled by the Vault.
- The Vault's share token is a normal ERC-20 — farmable, transferable, composable.
- New ranges are simple: deploy a new Vault, users migrate at will.

## How Alien Base uses Bunni

Every Vault entry on the [Vaults](vaults.md) page that's labeled "V3" or "Bunni" uses this pattern. The flow is:

1. You Zap or Deposit into the Vault.
2. The Vault holds your share of the underlying V3 NFT.
3. You receive Bunni share tokens.
4. The share tokens are auto-staked into the Alien Base farming distributor for ALB rewards.

When you withdraw, the inverse happens: the share tokens redeem against the Vault's NFT, your share of the underlying liquidity is returned to your wallet.

## Range management

A Bunni Vault has a **fixed price range** for its underlying V3 NFT. Range design follows three categories:

- **Wide** — analyzed against up to 2 years of price history; designed to stay in range for another 1–2 years.
- **Narrow** — more aggressive; can drift out of range in weeks or months on volatile pairs.
- **Stable / LSD** — very tight ranges suited for pairs that rarely deviate (USDC/USDT, ETH/cbETH, etc.).

When a Vault drifts close to its boundary, a **new** Vault with refreshed bounds is deployed. Existing depositors can stay (and accept being out-of-range eventually) or migrate to the new Vault.

This is by design: predictable bounds let LPs reason about their position rather than being silently rebalanced. The trade-off — having to manually migrate — is what [Mothership](mothership.md) is built to automate.

## Source code

- Upstream: [`timeless-fi/bunni`](https://github.com/timeless-fi/bunni)
- Alien Base fork: [`alienbase-xyz/bunni`](https://github.com/alienbase-xyz/bunni) and [`alienbase-xyz/bunniv2`](https://github.com/alienbase-xyz/bunniv2)
- Zap helper: [`alienbase-xyz/BunniZap`](https://github.com/alienbase-xyz/BunniZap) (lightly adapted from upstream BunniZap)

## Audits

Alien Base's BunniHub usage is **unmodified** from the upstream Bunni audit scope. The BunniZap is **lightly adapted** and shares most of its lineage with the audited upstream zap. Full lineage and links: [Audits & Security](../audits-and-security.md).

## See also

- [Vaults overview](vaults.md)
- [Concentrated Liquidity (V3)](v3.md)
- [Mothership](mothership.md) — automates what Bunni Vaults leave manual.
