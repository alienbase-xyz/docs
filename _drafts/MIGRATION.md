# Migration plan: drafts → live docs

This is the cheat sheet for moving everything in `_drafts/` into the published documentation tree, plus what to do with the existing files that aren't being rewritten.

> *Last updated: {{today}}.*

## How to use this file

When you're ready to publish:

1. Read each section below.
2. Move / copy / delete files as indicated.
3. Replace `SUMMARY.md` with `_drafts/SUMMARY.md`.
4. Replace `README.md` with `_drafts/README.md`.
5. Search the published tree for `<!-- TODO:USER` and `{{cit}}` and `{{verify}}` markers; fill them in.
6. Delete `_drafts/` and `_research/` (or keep them around in `.gitignore`'d state for the next iteration).

## A. New / rewritten pages — replace existing or add new

These live in `_drafts/` and should land in the published tree at the path indicated in `_drafts/SUMMARY.md`.

| Draft path | Status vs. existing | Action |
| --- | --- | --- |
| `_drafts/README.md` | Replaces `README.md` | Move; delete old |
| `_drafts/SUMMARY.md` | Replaces `SUMMARY.md` | Move; delete old |
| `_drafts/contracts.md` | Replaces `contracts.md` | Move; delete old |
| `_drafts/audits-and-security.md` | New | Add |
| `_drafts/fees.md` | New | Add |
| `_drafts/glossary.md` | New | Add |
| `_drafts/changelog.md` | New | Add |
| `_drafts/data-and-analytics.md` | New | Add |
| `_drafts/roadmap.md` | Replaces `roadmap.md` | Move; delete old |
| `_drafts/alb-token.md` | Replaces `alb-token.md` | Move; delete old |
| `_drafts/alien-base-2-0.md` | New | Add |
| `_drafts/alien-base-dao/*` | Mix; see below | Per file (below) |
| `_drafts/escrowed-alb-esalb/README.md` | Replaces `escrowed-alb-esalb/README.md` | Move; delete old |
| `_drafts/escrowed-alb-esalb/eslp.md` | New | Add |
| `_drafts/escrowed-alb-esalb/vesting.md` | New | Add |
| `_drafts/escrowed-alb-esalb/real-yield.md` | New | Add |
| `_drafts/get-started/*` | New (3 files) | Add |
| `_drafts/trading/swap.md` | New | Add |
| `_drafts/trading/epsilon.md` | Replaces `trading-tools/epsilon.md` | Move to `trading/`; delete old |
| `_drafts/trading/epsilon-analytics.md` | New | Add |
| `_drafts/trading/limit-orders.md` | Replaces & merges `trading-tools/limit-orders-and-automated-strategies/README.md` + `limit-orders.md` + `range-orders.md` | Move; delete the three originals |
| `_drafts/trading/recurring-orders.md` | Replaces `trading-tools/limit-orders-and-automated-strategies/recurring-orders.md` | Move; delete old |
| `_drafts/trading/dca-orders.md` | New | Add |
| `_drafts/liquidity/vaults.md` | New | Add |
| `_drafts/liquidity/v3.md` | Replaces `alien-base-v3/README.md` | Move; delete old |
| `_drafts/liquidity/bunni.md` | New | Add |
| `_drafts/liquidity/v2-pools.md` | New | Add |
| `_drafts/liquidity/mothership.md` | New (hidden until launch) | Add but consider feature-flagging |
| `_drafts/tools-for-projects/token-generator/README.md` | Replaces `tools-for-projects/token-generator/README.md` | Move; delete old |
| `_drafts/tools-for-projects/listing-your-token.md` | New | Add |
| `_drafts/common-issues/pending-or-failed-transactions.md` | New | Add |
| `_drafts/common-issues/why-my-swap-reverts.md` | New | Add |
| `_drafts/common-issues/my-lp-is-out-of-range.md` | New | Add |
| `_drafts/archive/*` (6 files: README + 5 product pages) | New | Add |

### `_drafts/alien-base-dao/*` detail

| Draft path | Status vs. existing | Action |
| --- | --- | --- |
| `_drafts/alien-base-dao/README.md` | Replaces `alien-base-dao/README.md` | Move; delete old |
| `_drafts/alien-base-dao/dao-multisig.md` | Replaces `alien-base-dao/dao-multisig.md` | Move; delete old |
| `_drafts/alien-base-dao/alien-foundation.md` | New | Add |
| `_drafts/alien-base-dao/alien-labs.md` | New | Add |
| `_drafts/alien-base-dao/how-to-propose.md` | New | Add |
| `_drafts/alien-base-dao/aip-index.md` | New | Add |

## B. Existing pages — keep as-is, migrate to new path

These pages are already good. Don't rewrite. Move to the new path indicated in `_drafts/SUMMARY.md`.

| Existing path | New path |
| --- | --- |
| `escrowed-alb-esalb/changing-allowance.md` | `escrowed-alb-esalb/changing-allowance.md` (no path change) |
| `tools-for-projects/token-generator/faq.md` | `tools-for-projects/token-generator/faq.md` (no path change) |
| `trading-tools/limit-orders-and-automated-strategies/creating-a-strategy.md` | `trading/creating-a-strategy.md` |
| `trading-tools/limit-orders-and-automated-strategies/faq/README.md` | `trading/faq/README.md` |
| `trading-tools/limit-orders-and-automated-strategies/faq/order-execution.md` | `trading/faq/order-execution.md` |
| `trading-tools/limit-orders-and-automated-strategies/faq/limit-vs-range-prices.md` | `trading/faq/limit-vs-range-prices.md` |
| `trading-tools/limit-orders-and-automated-strategies/faq/strategy-roi.md` | `trading/faq/strategy-roi.md` |
| `trading-tools/limit-orders-and-automated-strategies/faq/order-dynamics.md` | `trading/faq/order-dynamics.md` |
| `common-issues/rpc-troubleshooting-guide.md` | `common-issues/rpc-troubleshooting-guide.md` (no path change) |
| `common-issues/managing-token-allowance-guide.md` | `common-issues/managing-token-allowance-guide.md` (no path change) |
| `brand-kit.md` | `brand-kit.md` (no path change) |

After moving, scan each migrated file for stale links that reference the old paths (e.g., `../range-orders.md`) and fix.

## C. Existing pages — delete

These are superseded by the new structure or contain stale information that's better lost than refactored.

| Existing path | Why delete |
| --- | --- |
| `trading-tools/limit-orders-and-automated-strategies/range-orders.md` | Merged into `trading/limit-orders.md` |
| `alien-base-v3/v3-contracts.md` | Superseded by `contracts.md` (master list) |

## D. Things to do post-migration

1. **Fill TODOs.** Search for `<!-- TODO:USER`, `{{cit}}`, `{{verify}}`. Replace with concrete data.
2. **Replace `{{today}}`** with actual dates per page (or set up a build-time substitution).
3. **Move screenshots** from `_drafts/screenshots/` to `.gitbook/assets/` and update relative paths. See [SCREENSHOTS.md](SCREENSHOTS.md) for the full inventory + the wallet-state screenshots still needed.
4. **Verify cross-links.** Run the GitBook integrity checker (or `markdown-link-check`) to catch any broken `(path/to/file.md)` references.
5. **Mothership feature flag.** `_drafts/liquidity/mothership.md` is shipped but content references "pre-launch" / "audit in flight". Decide whether to publish behind a "Coming soon" banner, hide from `SUMMARY.md` until launch, or publish openly.
6. **Update Discord onboarding messages / pinned messages** to point to the new doc locations.
7. **Repo housekeeping.** Decide what to do with `_research/` — keep as internal reference, or delete now that the public docs are written.

## Open data points (rolled up for convenience)

These came up across multiple pages; gather once, plug everywhere:

- **Discord channel ID for the governance / proposals room** (currently linked to a generic Discord invite).
- **Telegram link** if it gets reactivated (currently removed per user direction).
- **DAO Multisig signer ↔ name mapping** (the eight signer addresses are listed in `_drafts/alien-base-dao/dao-multisig.md`; current public docs only listed 6 and called it 4-of-6).
- **VestingFactory address** + per-recipient instances list.
- **esLP token address** for ALB-ETH (and any others).
- **Foundation public name** + supervisors + reporting cadence.
- **Labs headcount** + hiring channels + retrospective cadence.
- **Real Yield**: most recent month's distribution (WETH amounts), implied APR, claim cadence and contract.
- **Mothership**: deployed addresses, fee schedule, initial strategy list, emergency-pause controller.
- **AIP-5 rollout**: cap-raise execution date, esALB protection program implementation status, public LoC dashboard URL.
- **Fee history dates**: confirmed numbers are now wired in (V2 0.16%; V3 7 tiers at 50/50; Epsilon 0.03/0.20; Carbon 0.40%; DCA same as Epsilon). Open: exact dates the V3 split moved 60/40 → 50/50, the V3 tier ladder expanded from 4 → 7 tiers, the Carbon 0.40% fee was introduced, and DCA migrated from a flat 0.1% to the Epsilon-mirroring schedule.
- **Discontinuation dates** for Predictions, Lottery, StableSwap.
- **B3 deployment ship date** + B3-chain contract addresses.
- **Token Generator launch month** in 2024.
- **DexScreener listing discount** terms for Token-Generator-deployed tokens.
- **Currently-active Vaults list** with full APR breakdown (ideally from a backend feed, not hand-listed).
