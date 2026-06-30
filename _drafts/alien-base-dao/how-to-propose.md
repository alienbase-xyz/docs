---
description: How to submit a proposal to the Alien Base DAO
---

# How to Propose

A practical guide for ALB holders who want to submit a proposal.

> *Last updated: {{today}}.*

## Before you start

You need:

- **At least 100,000 ALB of voting power**, in **esALB** form (or supported esLP variants), at the snapshot block.
- An **EVM wallet** that owns those tokens.
- A clear thesis. Vague proposals lose votes regardless of how good the underlying idea is.

If you don't have the threshold yourself, it's normal to **co-author with a larger holder**: draft your idea, get feedback in Discord, and either persuade a delegate to submit it on your behalf, or aggregate small holders into a delegation pattern. The DAO is small enough that this is a manual conversation, not a formal process — start in [Discord](https://discord.gg/alienbase) governance channels.

## Step 1 — Draft

Every Alien Base proposal has three sections:

1. **Motivation.** Why we're doing this. What problem the proposal solves. Data, on-chain references, or links to discussion threads.
2. **Description.** What concretely happens if the proposal passes. This is where you specify on-chain actions: contract calls (function name, parameters), ALB amounts to disburse, addresses involved. The clearer this section, the easier the DAO Multisig's job.
3. **Result.** How the proposal achieves its goal. Side effects, drawbacks, mitigations. If it changes tokenomics, model the impact.

Keep proposals **single-purpose** when possible. Combined proposals (e.g., "approve a budget *and* change emissions *and* deploy a new contract") tend to invite "yes to A, no to B" splits that are hard to interpret.

## Step 2 — Discuss

- Post the draft in Discord first, in `#governance` (or the active equivalent).
- Iterate for at least a few days. Most strong proposals go through 2–3 revisions.
- If the proposal is large or strategic, post a long-form version on Medium so non-Discord users see it.
- A proposal that hasn't been pre-discussed is significantly less likely to pass — even if its content is good.

## Step 3 — Submit on Snapshot

1. Go to the [Alien Base Snapshot space](https://snapshot.org/#/alienbase-dex.eth).
2. Click **New proposal**.
3. Title: short, descriptive, prefixed with `AIP-N:` if it's a major change. (Day-to-day operational asks can skip the AIP prefix.)
4. Body: paste your **Motivation / Description / Result** sections.
5. Choose the voting type:
   - **Single choice:** the default. Two options: `Yes` and `No`.
   - **Approval / weighted:** for proposals offering several mutually exclusive paths (AIP-4 used "Prioritize DAO" vs. "Prioritize holders").
6. Voting period: **3 days** is standard. Use 5–7 only for very high-impact proposals.
7. Voting strategy: leave the default — Snapshot is configured to use the [`alienbase-dex.eth` strategies](https://github.com/alienbase-xyz/snapshot-strategies) which weigh ALB, esALB, and selected esLP holdings.
8. Snapshot block: typically the current block. If you want to exclude very recent acquirers (e.g., to discourage vote-buying), choose a block from a few days back, but **say so explicitly** in the proposal.
9. Submit. The 100,000 ALB voting-power check is enforced at submission.

## Step 4 — Communicate while voting is open

- Pin the proposal in Discord.
- Cross-post on X (the Alien Base account will normally amplify well-formed proposals).
- Hold AMA / "office hours" if the topic is technical. AIP-2, AIP-4, and AIP-5 all had multiple Discord discussion sessions during the voting period.
- Be available to answer voter questions. Silence is a yellow flag.

## Step 5 — After it passes

If the proposal includes on-chain actions:

- The DAO Multisig signers (or, increasingly, the [Alien Foundation](alien-foundation.md)) queue the actions in the Safe.
- Time-locked actions (emission changes, ALB minting) wait out the timelock before execution.
- Track execution on the Safe's [Basescan page](https://basescan.org/address/0x4ab9070b7680f802cbf8322e597a4409902171e5) — every executed transaction is public.

If the proposal includes off-chain actions (operating budget, marketing, partnerships):

- Alien Labs (under the Foundation) executes within the approved budget.
- Status updates land in Discord and the next quarterly retrospective.

## Step 6 — If it doesn't pass

- Read the comments. Most rejected proposals have a fixable flaw — wrong scope, missing data, ambiguity.
- Iterate and re-submit. There's no cooldown.
- Don't take it personally. The DAO has rejected proposals from the founders too.

## Things that get proposals killed

- Numbers that don't add up. Run the math twice.
- Insufficient on-chain detail in the Description. "Pay the team" is not actionable; "transfer 1,000,000 ALB from the DAO Multisig to `0x…` over the next 6 months" is.
- Sneaking sub-items past voters by burying them in long sections.
- Conflicts of interest the proposer hasn't disclosed.
- Proposals that materially benefit a small group at the expense of the broader esALB base.

## Templates

We don't ship a heavyweight template. Read the existing AIPs (linked from the [AIP Index](aip-index.md)) and match their structure. AIP-2, AIP-3, ADIP-01, and AIP-5 are particularly good models for, respectively: emission tweaks, halving-cycle budgets, operating-budget proposals, and tokenomics overhauls.
