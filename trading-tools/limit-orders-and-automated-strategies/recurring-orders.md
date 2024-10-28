# Recurring Orders

Enable linked buy and sell orders to trade perpetually. An innovative approach to automated trading strategies, akin to grid trading or using a DEX trading bot, recurring orders revolve around repeating "buy low, sell high" trades.

For instance, you could set a recurring order to buy ETH from $1,900 to $1,800 and sell it from $2,100 to $2,200, with the ability to initially fund one or both orders.

Once tokens are acquired in a buy order for example, the liquidity automatically rotates and funds the linked sell order, creating a self-perpetuating trading loop. This cycle operates continuously without needing manual intervention, allowing users to compound profits through a custom, self-sustaining trading strategy.

<figure><img src="../../.gitbook/assets/Screenshot 2024-09-18 at 20.42.24.png" alt=""><figcaption><p>Recurring Order</p></figcaption></figure>

Recurring Orders have:

*   **Rotating Liquidity**

    Tokens acquired in a buy order instantaneously fund the linked sell order and vice versa. Compound profits with a custom trading strategy designed to run continuously.
* **Provide just one or both tokens** \
  With rotating liquidity, users are able to create orders with tokens they don't yet have, giving them the option to add liquidity to just one of the linked buy and sell orders.
* **Adjustable** \
  Easily edit without withdrawing funds. Adjust orders on-chain, saving time and gas.
*   **No Trading or Gas Fees on Filled Orders**

    Makers pay no gas when a trade is executed.
* **Irreversible** \
  Once orders are filled, they will not be undone should the market retrace.
* **Partial Fills** \
  Orders can be partially filled and remain irreversible.
* **Zero Slippage** \
  The price you set is what you'll receive.
*   **MEV - Sandwich Attack Resistant**

    Due to it's irreversible nature.
