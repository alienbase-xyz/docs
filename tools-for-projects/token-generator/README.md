# Token Generator

The Alien Base token generator allows you to create your own token or memecoin on Base without knowing any code.

These are the tokens you can currently create:

* **Simple token** with no extra features. Easy and sturdy, good for memecoins or other simple tokenomics.
* **Mintable token** with the ability to mint new tokens starting from an initial supply. Good for farms and DeFi tokens, but it's usually considered a red flag for memecoins.
* **Burnable token** with the ability to burn tokens. This is useful for when you have unique deflationary tokenomics.
* **Mint/Burn** token combines minting and burning, which is useful for some unique farming tokenomics.
* **Taxable Token** charges an additional fee on trading volume that is collected by the token. It's useful for gradually increasing the liquidity on the token and for funding future marketing campaigns. Many successful memecoins use this template for their projects.

### Contracts

The token generator uses factories to generate template tokens. All the tokens come as automatically verified by the blockchain explorer.

The **Simple, Mintable and Burnable** contracts use OpenZeppelin templates which have been proven for their reliability and sturdiness over time.

The **Tax Token** is based on existing popular coins including Toshi, Mochi, TYBG and others, ultimately tracing its architecture to the original EVM memecoins like SafeMoon and Shiba.

The list of factories is here:

| Type            | Address                                                                                                                                                      |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Simple Token    | [https://basescan.org/address/0x3b01457255bD6ec460D9Ab8f31CFabd8a710D176](https://basescan.org/address/0x3b01457255bD6ec460D9Ab8f31CFabd8a710D176)           |
| Mintable Token  | [https://basescan.org/address/0x6a9668c2C6E1FB107021375BaCD9d92e79cc8369](https://basescan.org/address/0x6a9668c2C6E1FB107021375BaCD9d92e79cc8369)           |
| Burnable Token  | [https://basescan.org/address/0xF5A7A624f4c11F581eb5a2B12e9bcA327F692c79](https://basescan.org/address/0xF5A7A624f4c11F581eb5a2B12e9bcA327F692c79)           |
| Mint/Burn Token | [https://basescan.org/address/0x872521B46095139e70A38AE3e8d95611649AAF51](https://basescan.org/address/0x872521B46095139e70A38AE3e8d95611649AAF51)           |
| Tax Token       | [https://basescan.org/address/0x13De15f0c5E8CC78Ad3a7001bA2Cb882aaE96373#code](https://basescan.org/address/0x13De15f0c5E8CC78Ad3a7001bA2Cb882aaE96373#code) |

For a full instruction on how to use the Token Generator, check out the FAQs at the Token Generator page or here in the Docs.



