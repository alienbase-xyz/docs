# Creating a Strategy

This guide walks you through creating a strategy on [app.alienbase.xyz](https://app.alienbase.xyz)

We'll create a recurring strategy with ETH and USDC that buys ETH between $2000 and $2100 and sells ETH between $2500 and 2600. We will fund the strategy with USDC tokens only.

### 1. Select Limit or Recurring on the swap page

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-18 at 20.14.49.png" alt=""><figcaption><p>Alien Base's Swap page on Recurring Order form</p></figcaption></figure>

In this case we will select Recurring, since we want to create a strategy that automatically buys low and sells high, rotating liquidity automatically between buy and sell.

### 2. Select pair

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-18 at 20.18.00.png" alt=""><figcaption><p>Pair selector</p></figcaption></figure>

Any pair of standard ERC20 tokens is valid. The “Buy or Sell” token (or “Base token”) is the token we would like to buy low and sell high, in this case ETH. The “With token” (or “Quote token”) is the token we would like to denominate rates in, in this case USDC.&#x20;

### 3. Select limit or range price

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-18 at 20.35.10.png" alt="" width="375"><figcaption><p>Limit (fixed) price</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-18 at 20.34.16.png" alt="" width="375"><figcaption><p>Price Range</p></figcaption></figure>

When selecting the price at which to execute the order, you can always choose to set a Range instead of an exact price. This way the buy and sell orders will be executed continuously inside the respective ranges, instead of being executed once at a fixed price. [Read more about Range Orders](range-orders.md).

In addition, you can always choose to insert the price in US Dollars for ease with the "$" toggle. In this case, being the "Quote Token" already USDC, it wouldn't make a difference.

### 4. Select buy/sell price range and budget

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-18 at 20.42.24.png" alt=""><figcaption><p>Setting of the Recurring Order</p></figcaption></figure>

The Sell Range is set to $2500-$2600. Meaning the strategy will start selling ETH at $2500 (“Min”) and stop selling ETH at $2600 (“Max”).

We fund the Sell Budget with 0 ETH.

The Buy Range is set to $2000-$2100. Meaning the strategy will start buying ETH at $2100 (“Max”) and stop buying ETH at $2000 (“Min”).

We fund the Buy Budget with 1000 USDC. Our USDC will be converted into ETH whenever the ETH market price enters the Buy Range.

### 5. Create and manage the strategy

You can now approve the required tokens and execute the transaction that funds the strategy.

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-18 at 20.49.07.png" alt="" width="173"><figcaption><p>Strategy Card</p></figcaption></figure>

In your [Dashboard](https://app.alienbase.xyz/liquidity), you can see all the Automated Strategies, and for each one you can deposit new funds, withdraw funds, edit prices and delete.

By clicking up-right on the card, or the general "Activity" tab, you can see all the history of your strategy, from when it was created to what trades were executed.

#### For any doubts or questions, open a ticket on [Discord](https://discord.com/channels/1151515107587792896/1151602990860484618) or check the dedicated [FAQ](faq/) page&#x20;
