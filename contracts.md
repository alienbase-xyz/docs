# 🧠 Alien Base Contracts

Below is the full list of verified smart contracts powering **Alien Base** on the **Base Network**.

---

## 💎 Token Information

| Parameter | Details |
|------------|----------|
| **Ticker** | $ALB |
| **Contract** | [0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4) |
| **Max Supply** | 510,000,000 ALB |
| **Initial Supply** | 26,000,000 ALB (5.1%) |

---

## ⚙️ DEX Core Contracts

| Component | Address | Description |
|------------|----------|--------------|
| **Factory** | [0x3e84d913803b02a4a7f027165e8ca42c14c0fde7](https://basescan.org/address/0x3e84d913803b02a4a7f027165e8ca42c14c0fde7) | Main liquidity factory contract for Alien Base DEX |
| **Router** | [0x8c1A3cF8f83074169FE5D7aD50B978e1cD6b37c7](https://basescan.org/address/0x8c1A3cF8f83074169FE5D7aD50B978e1cD6b37c7) | Routing contract handling swaps and liquidity operations |
| **Farm Contract** | [0x52eaecac2402633d98b95213d0b473e069d86590](https://basescan.org/address/0x52eaecac2402633d98b95213d0b473e069d86590) | Core farming and staking contract |

#### 🔒 Farm Security Details

- Controlled by **Selective Timelock Proxy:** [0x16f1F80654F2FEA97293321675907CFA2e23e4fB](https://basescan.org/address/0x16f1F80654F2FEA97293321675907CFA2e23e4fB)  
- Privileged operations (e.g., owner changes, emission rate updates) are **timelocked**  
- **Adding new farms / updating existing ones** — allowed **without timelocks** for quick market response  
- **Deposit fees** = 0% (permanently locked at zero after launch)

---

## 🛰️ Area 51 Contracts

| Contract | Address | Description |
|-----------|----------|--------------|
| **Router** | [0x837d9B4139dFbAc869b2c67771730bC822863376](https://basescan.org/address/0x837d9B4139dFbAc869b2c67771730bC822863376) | Custom router handling Area 51 swap mechanics |
| **Factory** | [0x2d5dd5fa7B8a1BFBDbB0916B42280208Ee6DE51e](https://basescan.org/address/0x2d5dd5fa7B8a1BFBDbB0916B42280208Ee6DE51e) | Factory contract for Area 51 pools |

---

## 🧬 esALB Contracts

| Component | Address | Description |
|------------|----------|--------------|
| **esALB Token** | [0xe1afc637f41e05efe08d55296a2ccff0072a4587](https://basescan.org/address/0xe1afc637f41e05efe08d55296a2ccff0072a4587) | Escrowed ALB token used for staking rewards and governance |
| **esMaster (Config)** | [0xd3968a4a07d64c6e16982d45191b9a09a261ec88](https://basescan.org/address/0xd3968a4a07d64c6e16982d45191b9a09a261ec88) | Master configuration and emission controller for esALB |
| **esALB-ETH Pair** | [0x176ca19007b1e2c9d85b8ecd68f89bb7f8a208f0](https://basescan.org/address/0x176ca19007b1e2c9d85b8ecd68f89bb7f8a208f0) | Main liquidity pair for esALB and ETH |

---

🛸 **Alien Base** — powering secure, transparent, and efficient DeFi on **Base Network**.
