---
description: A list of questions and answers about the Token Generator
---

# FAQ

#### How much does it cost to generate a token?

The fee for deploying a token is a flat 0.015 ETH no matter the features. The fee is paid in ETH and is non-refundable.

#### What should I put as Initial Token Supply?

Any number of tokens that you like, the more tokens you mint, the less value each token will have. Good practice is to make it between a few millions and up to a few trillion.

#### What should I put as Max Token Supply?

This is the maximum number of tokens that can be minted. It should always be higher than the initial token supply.

**What should I put as Max Token Supply?**

This is the maximum number of tokens that can be minted. It should always be higher than the initial token supply.

#### Should I enable the Mintable Feature?

If you enable the Mintable feature, you can mint more tokens after the token is created. This can be useful if you want to create a farm or airdrop tokens to your community, but it is usually seen as a red flag by traders and automated sniffers.

#### Should I enable the Burnable Feature?

If you enable the Burnable feature, users can burn their tokens and remove them from the circulating supply by interacting directly with the contract. This can be useful to increase the value of the token in the long term and to sustain the price.

#### Can I activate Mintable and Burnable features with the fee feature?

No, once you activate the fee feature, you can't activate the Mintable and Burnable features. Soon, there will be more combinations of tokens to create.

#### Can I collect fees on other DEXes than Alien Base?

When you enable the fees feature, the pool is automatically created on AlienBase, but you still need to add liquidity to it. Due to how tax token contracts work, there will always need to be liquidity on Alien Base, but you can add other DEXs for collecting fees (as long as you didn't renounce ownership).

#### I generated my Token, now what?

You can now create a pool on AlienBase by going to https://app.alienbase.xyz/add and adding your token and ETH to pair it with. You can also add logo and social information on BaseScan (https://basescan.org) to make your token look more professional. You can also list your token on DexScreener, Coingecko, GeckoTerminal, and DexTools to increase visibility and trust with your community.

#### How do I create a pool for my token?

You can make a pool on AlienBase by going to https://app.alienbase.xyz/add and adding your token and ETH to pair it with. For most cases, a full range V2 pool will be the best choice. You can set the initial price and the amount of liquidity you want to provide. After creating the pool, you will receive LP tokens that represent your share of the pool. To create additional trust, you can lock the LP or burn them by sending them to the dead address: 0x000000000000000000000000000000000000dEaD.

#### Can I create a V3 pool for my token?

You can only create V3 pools with non-tax tokens, so just Simple, Mintable, and Burnable. V3 pools allow you to increase the fee that users pay up to 1%, set your own initial price, and liquidity within specific ranges.

#### How do I lock my LP tokens?

You can lock your LP token on https://gempad.app or other apps including Team Finance, Floki Locker, and many others. By locking your LP tokens, you can create trust with your community as it's a way to prevent rug pulls.

#### How do I make a farm with my token?

You have to enable the Mintable feature and transfer ownership to the farming contract (MasterChef) of the DEX you want to launch the farm with. If you want to make a farm with your token on Alien Base, open a ticket on our Discord, and we will help you.

#### How do I burn tokens?

You will need to enable the Burnable feature, which allows users to burn tokens by interacting with the contract on the explorer page. By calling the burn function, any user can burn their tokens, and they get removed from the circulating supply. Sending tokens to the burn address is also a way to burn tokens, but doesn't remove them from the circulating supply.

#### Where do the fees get collected?

Trading fees are either accumulated as liquidity or sent directly to the creator address you used to deploy the token. The liquidity is stored on the Token contract and cannot be withdrawn directly, but it increases the liquidity and attractiveness of the token.

#### How do I renounce ownership?

You can renounce ownership by calling the renounceOwnership function in the contract. This will remove the owner from the contract and make it impossible to change the owner address again.

#### Do I always need to renounce ownership?

The Simple and Burnable tokens have no ownership, so there's nothing to renounce. Mintable and Tax Tokens can be renounced, which is usually an additional sign of trust from the community, but it is best to do it when you know you won't need to change any of the parameters of the token.

#### Can I withdraw the fees that go to LP on the Tax Token?

No, fees that go to LP are automatically added to the liquidity pool and cannot be withdrawn by the owner.

#### How do I change the fees on the Tax Token?

If you didn't renounce ownership, you can change the fee percentages by calling the setBuyFees, setSellFees, and setFeeSplit functions in the contract. The fees are set in wei points, so a fee of 1% would be set as 10.000.000.000.000.000. Use the Basescan explorer to convert percentages to wei points.

#### How do I change the fee recipient address on the Tax Token?

You can change the recipient address by calling the setDevelopmentWallet function in the contract. This changes the address that receives the fees. It can be called by the creator of the contract or the existing recipient address. This is useful to change the fee recipient wallet, even if ownership is renounced.

#### How do I change the owner/creator address?

You can change the owner address by calling the transferOwnership function in the contract. The owner address is the address that can mint new tokens on Mintable tokens, and change the fee settings on the Tax Token.

#### How do I interact with the chain explorer?

You can interact with the chain explorer by connecting your wallet and interacting with the contract. You can view the contract code, read the contract state, and interact with the contract functions. You can also view the contract events and transactions on the explorer page. For Base, the chain explorer is https://basescan.org.

#### How do I add the token logo and social info in the chain explorer?

By logging in with the owner wallet, you can update the token logo and social info on the chain explorer. This information will be picked up by many other services like DexScreener, DexTools, and wallets like MetaMask. Visit https://basescan.org and make an account with the owner wallet to update the token info.

#### How do I list my token on DexScreener?

Tokens get picked up automatically as soon as there is at least one transaction on the blockchain. However, they don't show any logo or information about the token. To add your logo and social info, you can visit this page: https://marketplace.dexscreener.com/product/token-info. The listing fee is 300$, but we will soon have a discount for tokens that are created on Alien Base.

#### How do I list my token on CoinGecko?

You can request listing your token on CoinGecko by filling out this form: https://www.coingecko.com/en/coins/new.

#### How do I list my token on GeckoTerminal?

On GeckoTerminal, tokens get picked up automatically as soon as there is at least one transaction on the blockchain, but you can add token logo and social information for free by visiting the token page and clicking on the 'Update Token Info' button.

#### How do I list my token on DexTools?

On DexTools, tokens get picked up automatically as soon as there is at least one transaction on the blockchain. However, they don't show any logo or information about the token. To add your logo and social info, you can visit this page: https://www.dextools.io/app/en/base/pairs and click on the 'Update Token Info' button. By adding information about your token on CoinGecko or the Chain Explorer (BaseScan), you will also have the information updated on DexTools.

#### How do I list my token on CoinMarketCap?

Listing a token on CoinMarketCap is a bit more complicated than on other services. You can request listing your token on CoinMarketCap by filling out this form: https://coinmarketcap.com/request. For the vast majority of projects, the only realistic way to be listed is by paying a $5,000 fee for "priority" access.
