---
description: A focused guide to the four most common swap-revert causes
---

# Why my swap reverts

If your swap reverts (= the transaction goes through but the swap doesn't happen, and you pay gas), one of four things is almost always responsible. Walk through them in order.

> *Last updated: July 6, 2026.*

## 1. Slippage too low

By far the most common cause.

**What happened.** You set slippage at, say, 0.5%. Between the moment Alien Base quoted your trade and the moment the chain executed it, price moved more than 0.5%. The swap has a built-in safety check that aborts if price moves more than your tolerance — so it reverted.

**Fix.** Raise slippage in the swap UI Settings (gear icon).

| Pair type | Suggested slippage |
| --- | --- |
| Stablecoin / blue chip | 0.1–0.5% |
| Standard alts | 0.5–1% |
| Volatile / low liquidity | 2–5% |
| Memecoins with on-trade fees | 5–15% |

**Don't go higher than you need.** Excessive slippage exposes you to MEV sandwich attacks. Find the lowest value that lets the trade execute reliably for the pair you're trading.

## 2. Token has a transfer fee (fee-on-transfer)

Many memecoin templates take a fee on every transfer. The fee silently reduces what arrives at the destination.

**What happened.** Alien Base quoted "you'll receive 1,000 TOKEN" but TOKEN takes a 5% transfer fee, so only 950 actually arrived — below your slippage threshold. Revert.

**Fix.** Increase slippage to cover the on-transfer fee plus a buffer. For a 5% fee, a slippage of 6–7% is typically enough.

The Alien Base swap UI shows a warning when it detects a known fee-on-transfer token, but it can't always detect them. If the contract is unfamiliar, check Basescan for `_taxFee` / `_buyFee` / `_sellFee` style state variables.

## 3. Insufficient allowance

**What happened.** You approved a router previously for some amount, but the current swap exceeds that approved amount. Or the approval transaction itself never landed.

**Fix.** Re-approve the router for the token (the swap UI will prompt you with an Approve button if it detects the issue). If your approve transaction succeeded but the swap still fails:

- For ALB → esALB specifically, see [Changing allowance](../escrowed-alb-esalb/changing-allowance.md).
- For general allowance issues, see [Managing Token Allowance](managing-token-allowance-guide.md).

## 4. Liquidity moved between quote and execution

**What happened.** The pool you were going to swap against had its liquidity removed, or its price moved into a zone where the swap is no longer possible at your quote, between when the quote was computed and when the chain executed your tx.

**Fix.**

- Refresh the quote and try again.
- If the same pool keeps reverting, swap in a different size — sometimes a smaller amount can route through alternative pools.

## Other less-common causes

- **Insufficient ETH for gas.** You can't pay gas without ETH on Base. Bridge or buy ~$1 worth.
- **Insufficient balance.** Self-explanatory; double-check.
- **Wrong network.** You may be on Ethereum mainnet by mistake. The Alien Base UI will warn if so.
- **Deadline expired.** Some transactions have a deadline parameter; if your tx was pending in the mempool too long, the deadline can pass. Speed-up via the wallet, or just resubmit.

## How to read the actual revert reason

Open the failed tx on [Basescan](https://basescan.org/). The "Revert reason" field is usually populated. Common messages:

- `INSUFFICIENT_OUTPUT_AMOUNT` → slippage / fee-on-transfer (#1 or #2 above).
- `TRANSFER_FROM_FAILED` → allowance (#3) or fee-on-transfer behavior.
- `EXPIRED` → deadline passed.
- `UniswapV3: SPL` → V3 pool sub-tick computation issue, almost always slippage-adjacent on a low-liquidity pool.

If you can't figure it out, post the tx hash in [Discord](https://discord.gg/alienbase) and someone will look at it.
