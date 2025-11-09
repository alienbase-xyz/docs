# Token Generator

The Alien Base Token Generator allows you to create your own token or memecoin on Base — no coding skills required.

These are the token types currently supported:

* **Simple Token** — no extra features. Straightforward and reliable; perfect for memecoins or simple tokenomics.
* **Mintable Token** — allows minting of new tokens after the initial supply. Ideal for farms and DeFi tokens, though often seen as a red flag for memecoins.
* **Burnable Token** — enables token burning, supporting deflationary tokenomics.
* **Mint/Burn Token** — combines both minting and burning, suited for dynamic farming mechanics.
* **Taxable Token** — applies a transaction fee collected by the token itself. Useful for increasing liquidity or funding marketing campaigns. Popular among successful memecoins.

---

### Contracts

The Token Generator uses factory contracts to deploy verified templates on-chain.  

**Simple**, **Mintable**, and **Burnable** token contracts are based on **OpenZeppelin** templates — known for reliability and security.  

The **Tax Token** derives from successful memecoin architectures such as *Toshi*, *Mochi*, *TYBG*, *SafeMoon*, and *Shiba Inu*.

| Type            | Factory Address                                                                                                                                            |
| ---------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Simple Token     | [0x3b01457255bD6ec460D9Ab8f31CFabd8a710D176](https://basescan.org/address/0x3b01457255bD6ec460D9Ab8f31CFabd8a710D176) |
| Mintable Token   | [0x6a9668c2C6E1FB107021375BaCD9d92e79cc8369](https://basescan.org/address/0x6a9668c2C6E1FB107021375BaCD9d92e79cc8369) |
| Burnable Token   | [0xF5A7A624f4c11F581eb5a2B12e9bcA327F692c79](https://basescan.org/address/0xF5A7A624f4c11F581eb5a2B12e9bcA327F692c79) |
| Mint/Burn Token  | [0x872521B46095139e70A38AE3e8d95611649AAF51](https://basescan.org/address/0x872521B46095139e70A38AE3e8d95611649AAF51) |
| Tax Token        | [0x13De15f0c5E8CC78Ad3a7001bA2Cb882aaE96373](https://basescan.org/address/0x13De15f0c5E8CC78Ad3a7001bA2Cb882aaE96373#code) |

---

For complete instructions on using the Token Generator, refer to the **FAQs** on the Token Generator page or within the **Documentation**.
