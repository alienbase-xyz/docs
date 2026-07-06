---
description: Deprecated isolated-fee-tier DEX
---

# Area 51 (deprecated)

**Status:** deprecated. Liquidity was migrated and the product was removed from the main UI in 2024.

> *Last updated: July 6, 2026.*

## What it was

Area 51 was an isolated, separately-deployed fork of Alien Base's V2 contracts — a standalone DEX with its own factory, router, and farm, built to host higher-fee or experimental pools without touching the main V2 deployment.

The original docs framed Area 51 as an "experimental fee-tier sandbox," which it largely was. It had limited adoption and was eventually phased out as Alien Base V3 (concentrated liquidity, configurable fee tiers natively) made an isolated experimental DEX redundant.

## The "Area 51" name today

Area 51 has been **rebranded internally** as the umbrella name for Alien Base's developer-tooling suite — the [Token Generator](../tools-for-projects/token-generator/README.md) is part of this suite. So "Area 51" in current Alien Base communication usually refers to the dev tools, not the deprecated DEX.

## Contracts (historical)

For verification purposes — these contracts are still on-chain but no longer surfaced in the dApp:

- **Factory:** [`0xa0F4f3b13f5eE9b56cca59cB4F7CDd0b40fE9c50`](https://basescan.org/address/0xa0F4f3b13f5eE9b56cca59cB4F7CDd0b40fE9c50)
- **Router:** [`0xfa1AcA9d83fc6B4d6BCAC56de1ECd1c5b83AC110`](https://basescan.org/address/0xfa1AcA9d83fc6B4d6BCAC56de1ECd1c5b83AC110)
- **Farm:** see [Contracts — Deprecated section](../contracts.md)

> Note: a previous version of these docs listed a different address for the Area 51 Router. Community PR #9 (UserIzanagi) flagged the mismatch; the address above is the verified one.

The Area 51 Factory `feeToSetter` is still controlled by a single team EOA (`0xa670…0166`) and was not migrated to the DAO Multisig before deprecation. As the contracts are no longer the venue of any meaningful activity, this is treated as low priority.

## If you have funds in Area 51

The contracts remain on-chain and remain functional. To withdraw:

1. Note your LP token address from the [Area 51 Factory's pairs](https://basescan.org/address/0xa0F4f3b13f5eE9b56cca59cB4F7CDd0b40fE9c50).
2. Call `removeLiquidity(...)` on the Area 51 Router directly via Basescan's "Write Contract" tab.
3. Or, if your LP is staked in the Area 51 Farm: `withdraw(pid, amount)` first, then remove liquidity.

If you can't figure it out, post in [Discord](https://discord.gg/alienbase) — the team can help walk through it.

## See also

- [Contracts — Deprecated section](../contracts.md)
- [Token Generator](../tools-for-projects/token-generator/README.md) — the current "Area 51" suite.
