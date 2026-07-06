---
description: Quick definitions for terms used across Alien Base
---

# Glossary

A short reference for terms you'll see repeatedly in Alien Base's docs and UI.

> *Last updated: July 6, 2026.*

### ADIP

*Alienbase DAO Improvement Proposal.* A governance proposal authored by the [Alien Foundation](alien-base-dao/alien-foundation.md) (rather than an individual address). Used for operating-budget proposals and Foundation-administered actions. See [ADIP-01](https://snapshot.org/#/alienbase-dex.eth/proposal/0xae936ad8ddb58b90128ff8da95bb6edded6188ba4c87f2ea724d771cfcc17cac) for the canonical example.

### AIP

*Alienbase Improvement Proposal.* A governance proposal voted on at [`alienbase-dex.eth`](https://snapshot.org/#/alienbase-dex.eth). Anyone holding 100,000+ ALB of voting power can submit one. Index: [AIP Index](alien-base-dao/aip-index.md).

### ALB

The native token of Alien Base. ERC-20 on Base. [`0x1dd2…50c4`](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4). See [ALB Token](alb-token.md).

### ALM (Automated Liquidity Manager)

A protocol that actively manages V3 (concentrated-liquidity) positions on behalf of LPs. Alien Base's ALM is **Mothership** — see [Mothership](liquidity/mothership.md).

### Area 51

The original umbrella name for Alien Base's developer-tooling suite. Also the name of a now-deprecated isolated fee-tier DEX. The dev-tooling concept lives on through products like the [Token Generator](tools-for-projects/token-generator/README.md). The deprecated DEX is documented in the [Archive](archive/area-51.md).

### Base

The Coinbase-incubated, Optimism-stack, EVM-compatible L2 Alien Base lives on. Chain id: 8453. See [base.org](https://base.org).

### Bunni

A Uniswap V3 LP-position wrapper that turns NFT positions into ERC-20 tokens. Alien Base uses Bunni to make V3 positions composable, transferable, and farmable. See [Bunni explainer](liquidity/bunni.md).

### Carbon

Alien Base's former integration of Bancor's Carbon DeFi technology, which powered Limit, Range, and Recurring (grid) orders until July 2026. Deprecated in favor of the Epsilon Router order system; existing Carbon orders remain withdrawable. See [Archive — Carbon Orders](archive/carbon-orders.md).

### CEX-quality UI / UX

Shorthand the team uses for "trading and liquidity flows that feel like a CEX, but are still permissionless and self-custodial." It's the design north star for Alien Base.

### Concentrated Liquidity

A V3 LP design where LPs choose a price range for their liquidity rather than spreading it across the whole curve. Provides much higher capital efficiency at the cost of being out-of-range when price moves. See [V3](liquidity/v3.md).

### DCA

Dollar-Cost Averaging. Splits a buy or sell into small chunks executed over time, with optional trigger price and stop loss. Fees per chunk are tiered by asset class (0.01% stables / 0.10% blue chips / 0.20% other). See [DCA Orders](trading/dca-orders.md).

### Epsilon

Alien Base's trading engine: the meta-aggregator that routes swaps through whichever venue (Alien Base V2/V3, Aerodrome, Uniswap, etc.) gives the best price, plus the on-chain **Epsilon Router** that holds and settles resting orders (Limit, Take Profit, Stop Loss, Trailing Stop, DCA). The **Explorer** exposes the underlying data. See [Epsilon](trading/epsilon.md).

### Epsilon Router

The on-chain contract ([`0x303c…2580`](https://basescan.org/address/0x303ca5c65AabCb1CE242DF93F478c41E0E4D2580)) where Alien Base's resting orders live. Audited; live since July 2026. See [Epsilon](trading/epsilon.md#the-epsilon-router).

### esALB / esLP

*Escrowed ALB / Escrowed LP.* Locked, non-transferable forms of ALB and select LP tokens that earn voting power, single-staking APR, and Real Yield. Convertible 1:1 with the underlying token; redemption paths are 100% in 30 days or 1% every 12 hours. See [esALB](escrowed-alb-esalb/README.md).

### Fair launch

A token launch with no pre-mine, no pre-sale, and no insider allocation released ahead of the public. Alien Base launched fair on August 8, 2023.

### Farming

Earning ALB rewards by staking LP tokens (or esALB / esLP) in the protocol's distributors. Historically the main user incentive; under [AIP-5](alien-base-2-0.md) farming is being phased out in favor of POL.

### Foundation

See [Alien Foundation](alien-base-dao/alien-foundation.md). The Cayman-registered, ownerless legal entity that gives the DAO offchain legal footing.

### govALB

A new staked-escrow form of esALB introduced by [AIP-5](alien-base-2-0.md): **10× voting power**, 1× earning power, ~2-year effective lock. Designed for users who want maximum governance influence and are willing to commit time.

### LoC (Line of Credit)

The Dev Line of Credit introduced by [AIP-5](alien-base-2-0.md): the team's funding becomes tracked debt with interest paid to esALB holders. Price-tier grant tranches at $0.40, $1, and $2 unlock as ALB sustains those moving averages. See [Alien Labs](alien-base-dao/alien-labs.md).

### Matcher

Epsilon's execution engine. Watches resting orders in the Epsilon Router and fills them through the meta-aggregator when their trigger condition is met, charging a flat 0.05% execution fee per fill. Users pay gas only at order creation/cancellation; the Matcher pays execution gas. See [Epsilon](trading/epsilon.md#the-matcher).

### Meta-DEX

The umbrella term Alien Base uses for itself. Combines a native DEX (V2 + V3), a meta-aggregator + on-chain order engine (Epsilon), liquidity management (Mothership), and developer tools (Token Generator) — all on a single platform.

### Mothership

Alien Base's in-house Automated Liquidity Manager (ALM). First fully-original Alien Base protocol (not a fork). Public alpha launches with strict supply caps after audit completion. See [Mothership](liquidity/mothership.md).

### POL (Protocol-Owned Liquidity)

Liquidity owned by the protocol itself — typically held in the DAO Multisig — rather than rented from individual LPs via emissions. AIP-5 establishes a POL Fund whose yield is used for buyback-and-burn ALB.

### Real Yield

Protocol fees redistributed to esALB stakers in WETH (and other liquid assets) — not in ALB inflation. See [Real Yield](escrowed-alb-esalb/real-yield.md).

### Snapshot

Off-chain governance voting platform. Alien Base's space: [`alienbase-dex.eth`](https://snapshot.org/#/alienbase-dex.eth).

### Stop Loss / Stop Buy

Orders that trigger when price crosses a level in the adverse direction: a Stop Loss sells when price drops to your level; a Stop Buy buys when price climbs to it. Executed on-chain by the Epsilon Router. See [Limit, Take Profit & Stop Loss](trading/limit-orders.md).

### Take Profit

A sell order that triggers when price climbs to your target. See [Limit, Take Profit & Stop Loss](trading/limit-orders.md).

### Timelock

A contract that delays execution of privileged actions (e.g., minting ALB, changing emission rates). Alien Base's farm controllers and ALB token use timelocks of 7 and 14 days respectively.

### Token Generator

A tool for deploying tokens on Base from preset templates (Simple, Mintable, Burnable, Mint/Burn, Tax). Charges a small ETH fee per mint, deposited to the team operating budget. See [Token Generator](tools-for-projects/token-generator/README.md).

### Trailing Stop

A sell order whose trigger follows the market price up by a fixed percentage and fires when price retraces by that amount from its peak. See [Trailing Stop](trading/trailing-stop.md).

### TVL (Total Value Locked)

The dollar value of assets sitting in a protocol's pools and vaults. Tracked on [DefiLlama](https://defillama.com/protocol/alien-base-v3).

### Vaults

The successor to "Farms" in the Alien Base UI. The single page that aggregates V3 / Bunni / esALB / esLP / future Mothership-managed positions. See [Vaults overview](liquidity/vaults.md).

### V2 / V3

Uniswap V2 and Uniswap V3 — the AMM architectures Alien Base implements. V2 is the original constant-product pool (50/50, full-range). V3 is concentrated-liquidity. See [Liquidity](liquidity/v3.md).
