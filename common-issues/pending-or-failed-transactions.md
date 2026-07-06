---
description: What to do when a transaction is stuck or reverted
---

# Pending or failed transactions

> *Last updated: July 6, 2026.*

## My transaction is stuck "Pending"

Base normally confirms transactions in 1–3 seconds. Stuck pending almost always means one of:

1. **Underpriced gas.** Your wallet quoted a base fee from a moment of low demand; demand spiked before your tx was included. Bump priority and resubmit.
2. **Network congestion.** Base sees brief congestion spikes. Usually clears in minutes.
3. **Nonce gap.** A previous tx from your wallet is stuck and yours is queued behind it.

### How to fix a stuck transaction

**Option A — Speed up.** In MetaMask / Rabby / Coinbase Wallet, find the pending tx in your activity → click **Speed up** → confirm. The wallet replaces the original tx with a higher-fee version using the same nonce.

**Option B — Cancel.** Same flow, but use **Cancel**. The wallet submits a 0-value self-transfer at the same nonce, replacing the stuck tx.

**Option C — Manual replacement.** If the wallet's UI doesn't expose Speed up / Cancel:
1. Note the nonce of the stuck tx (Basescan → your address → tx detail).
2. Send a 0-value tx to yourself with that exact nonce and a higher gas price.
3. Once that confirms, the chain advances past the stuck tx.

If you have multiple stuck transactions (e.g., a queue of approvals), you'll need to clear them in nonce order.

## My transaction reverted

A reverted transaction means the EVM evaluated the call and decided it couldn't be executed. You paid gas; nothing else happened.

Common causes by transaction type:

### Swap reverted

- **Slippage exceeded.** Set higher slippage in Settings (most common cause for memecoins or fee-on-transfer tokens). See [Why my swap reverts](why-my-swap-reverts.md).
- **Insufficient allowance.** Approve the router for the token, then retry. See [Managing Token Allowance](managing-token-allowance-guide.md).
- **Insufficient balance.** You're trying to spend more than you have, or you don't have enough ETH for gas.
- **Pool liquidity moved.** Quote was based on a price that no longer exists. Retry with a fresh quote.

### Liquidity (LP) tx reverted

- **Slippage on add/remove.** Each LP action has its own slippage tolerance.
- **Out-of-range range parameters.** For V3, the lower price must be below the upper price; both must be on a valid tick spacing.
- **Approval missing for one of the two tokens.**

### Lock / esALB tx reverted

- **Approval missing.** Approve ALB for the EsToken contract, then retry. If approve "succeeded" but Lock still fails, see [Managing Token Allowance](managing-token-allowance-guide.md) and the [Changing allowance](../escrowed-alb-esalb/changing-allowance.md) workaround.

### Generic — Basescan tells you why

Open the failed tx on Basescan. The "Revert reason" field often spells out exactly what happened in plain text (e.g., `Pancake: INSUFFICIENT_OUTPUT_AMOUNT`). When asking for help, paste the revert reason and the tx hash.

## I see a transaction I didn't make

If you see an unexplained transaction:

1. Check the `From` address. If it's not yours, you're seeing someone else's tx that touches your address (e.g., an airdrop, or someone sending tokens to you).
2. If `From` is your address and you didn't initiate it, you may have an unrevoked approval being abused. Immediately:
   - Move funds out of that address to a fresh wallet.
   - Revoke approvals on the compromised address using [revoke.cash](https://revoke.cash) or similar.
   - For esALB-specific approvals, see [Changing allowance](../escrowed-alb-esalb/changing-allowance.md).

## See also

- [RPC Troubleshooting Guide](rpc-troubleshooting-guide.md)
- [Managing Token Allowance](managing-token-allowance-guide.md)
- [Why my swap reverts](why-my-swap-reverts.md)
- [Changing allowance (esALB-specific)](../escrowed-alb-esalb/changing-allowance.md)
