# Screenshots inventory

> *Last updated: {{today}}.*

All draft screenshots live in `_drafts/screenshots/`. At migration time, move them to `.gitbook/assets/` and update the relative paths in the pages that reference them.

## Captured (autonomous, public/disconnected state)

| # | File | Captured by | Used on | Notes |
| --- | --- | --- | --- | --- |
| 01 | `01-swap-page.png` | agent | `trading/swap.md` | Swap tab, sidebar expanded |
| 02 | `02-limit-order.png` | agent | `trading/limit-orders.md` | Limit (single price) mode, "Powered by CARBON" footer visible |
| 03 | `03-range-order.png` | agent | `trading/limit-orders.md` | Limit Range sub-mode (Min/Max) |
| 04 | `04-recurring-order.png` | agent | `trading/recurring-orders.md` | Paired Sell-high / Buy-low view |
| 05 | `05-dca-order.png` | agent | `trading/dca-orders.md` | Includes the "ETH not supported, use WETH" inline warning |
| 06 | `06-farms-legacy.png` | agent | (not yet wired) | V2 farms list with 0% APR — represents the post-AIP-5 wind-down state |
| 07 | `07-dashboard-empty.png` | agent | `get-started/connecting-your-wallet.md` | Pretty hero shot, "Connect your wallet" empty state |
| 08 | `08-token-generator.png` | agent | `tools-for-projects/token-generator/README.md` | Form with Minting / Burning / Receive Fees toggles |
| 09 | `09-explorer-epsilon-analytics.png` | agent | `trading/epsilon-analytics.md` | Trending / Gainers / Losers / New tokens + main pair table |
| 10 | `10-new-position.png` | agent | `liquidity/v3.md` | New position landing — V2/V3 selector + pair picker |

## Still to capture (require connected wallet — please grab manually)

For each one, please save the file in `_drafts/screenshots/` with the suggested filename, then this doc will reference it from the right page.

### High priority

| # | Suggested filename | What to capture | Used on |
| --- | --- | --- | --- |
| 11 | `11-lock-modal.png` | Dashboard → click **Lock** on your ALB balance → the Lock modal with an amount filled in (don't submit) | `escrowed-alb-esalb/README.md` |
| 12 | `12-unlock-modal.png` | Dashboard → click **Unlock** on a locked esALB position → the modal showing the **30 days / 1% per 12h** options side by side | `escrowed-alb-esalb/README.md` |
| 13 | `13-vested-position.png` | Dashboard with at least one esALB position currently in 30-day vesting, countdown visible | `escrowed-alb-esalb/README.md` |
| 14 | `14-esalb-stake-card.png` | Vaults page → esALB Single Stake card with rewards accruing | `escrowed-alb-esalb/README.md` |
| 15 | `15-active-strategy-card.png` | Dashboard → an active Carbon Recurring strategy card with non-zero balance and price ranges visible | `trading/recurring-orders.md` and `trading/creating-a-strategy.md` |
| 16 | `16-strategy-history.png` | Click an active strategy → the Activity / history view showing recorded trades | `trading/recurring-orders.md` |
| 17 | `17-vaults-with-positions.png` | Vaults page when at least one V3 / Bunni Vault has a deposit, showing APR breakdown + Harvest button | `liquidity/vaults.md` |

### Medium priority

| # | Suggested filename | What to capture | Used on |
| --- | --- | --- | --- |
| 18 | `18-v3-position-detail.png` | Dashboard → V3 position detail page with chart, range markers, fees earned | `liquidity/v3.md` |
| 19 | `19-token-detail-explorer.png` | Explorer → click any active token (e.g., ALB) → token-detail page showing chart, top pools, GoPlus safety check | `trading/epsilon-analytics.md` |
| 20 | `20-pool-detail-explorer.png` | Explorer → click into a specific pool → pool-detail page with order book / trade history | `trading/epsilon-analytics.md` |
| 21 | `21-swap-route-detail.png` | Swap UI with a quote populated, route panel expanded showing multi-hop + percentage splits | `trading/swap.md` and `trading/epsilon.md` |
| 22 | `22-settings-modal.png` | Click the gear icon in the swap UI → settings modal with slippage / deadline visible | `trading/swap.md` |
| 23 | `23-wallet-connect-modal.png` | Click Connect Wallet → the wallet selector modal | `get-started/connecting-your-wallet.md` |

### Optional / nice-to-have

| # | Suggested filename | What to capture |
| --- | --- | --- |
| 24 | `24-token-deployed.png` | Token Generator after a successful deployment, with the "Deployed!" confirmation and contract link |
| 25 | `25-mothership-vault.png` | (post-launch) The Mothership Vault detail card |
| 26 | `26-govalb-flow.png` | (post-AIP-5 rollout) The govALB lock / vote-power-multiplier UI |
| 27 | `27-dao-vote.png` | A live or recent Snapshot proposal page (browser screenshot of `snapshot.org/#/alienbase-dex.eth`) |

## Tips for grabbing the wallet-state screenshots

- Use a clean test wallet if you don't want to expose real address activity. If using a real address, redact the wallet pill in the top-right after capture.
- Take screenshots at 1440×900 (or wider) to match the autonomous captures.
- Sidebar should be **expanded** (click the bottom-left "Collapse" button to toggle if needed) for consistency with the existing set.
- Save with the exact filename in the table above. The pages already reference these paths.
- For any modal screenshots, capture only the content area — the modal + any visible page context behind it. Don't capture full-page if the modal is the focus.

## What I learned from the captures (worth updating elsewhere)

The exploration surfaced a few things worth syncing into the docs:

1. **Trade modes are 4, not 5.** Swap / Limit / Recurring / DCA. "Range" lives inside Limit as a price-mode toggle. The new Limit Orders page already reflects this.
2. **The dApp's Limit/Recurring pages show "Powered by CARBON" attribution** explicitly. Worth keeping that branding consistent in the docs.
3. **DCA does not support raw ETH** — UI surfaces an inline warning recommending WETH. Now noted on the DCA page.
4. **Aggregator routing list** is OpenOcean / Odos / 0x / Bebop (visible in the Swap UI's Route panel) — different from the OpenOcean / ParaSwap list in the existing docs. Now corrected on the Epsilon page.
5. **Explorer DEX coverage** is broader than docs implied: Alien Base, Uniswap, Aerodrome, PancakeSwap, Sushiswap, BaseSwap, Solidly, DackieSwap, SwapBased. Now corrected on the Epsilon page.
6. **Token Generator UI shape** consolidates templates behind toggles (Minting / Burning / Receive Fees) rather than a 5-template picker. The contracts behind it are still the documented factories. Now reflected in the Token Generator page.
7. **`/farms` URL shows the legacy V2 farms list with 0% APR everywhere** — consistent with AIP-5's farming wind-down. The sidebar still calls this "Vaults" though. <!-- TODO:USER confirm whether the new V3/Bunni Vaults UI ships under a different route, or whether the new architecture is being added in-place to /farms. -->
8. **Sidebar nav has 5 entries:** Swap / Dashboard / Vaults / Explorer / Token generator. Confirms the new IA terminology.

## Migration

When moving to the live docs:

1. Move the `.png` files from `_drafts/screenshots/` to `.gitbook/assets/` (matches existing pattern).
2. Either rename them (drop the `01-` prefixes) or keep the prefixes — both work in GitBook.
3. Update the `![alt](_drafts/screenshots/XX-name.png)` references in each page to point to the new path. A quick search-replace will do it.
4. Optionally convert the inline `![alt](path)` syntax to GitBook's `<figure>` block (the existing pattern) for richer captioning.
