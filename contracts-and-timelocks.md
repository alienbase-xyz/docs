# Contracts & Timelocks

Token

* Ticker: $ALB
* Contract: [https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4](https://basescan.org/token/0x1dd2d631c92b1acdfcdd51a0f7145a50130050c4)
* Max Supply: 510 Million
* Initial supply: 5.1% (26 Million)
* 25 million ALB was placed behind a time lock contract at
  * &#x20;[https://basescan.org/tx/0x44d3753e8e0e104f4751665af885c77fc8ee338abd377496cb33b1a35b10aca9](https://basescan.org/tx/0x44d3753e8e0e104f4751665af885c77fc8ee338abd377496cb33b1a35b10aca9)
  * [https://basescan.org/tx/0x5936515cc428ce9d66396d995b490f059da4152c182e1e8f42dc7ce6a38fd278](https://basescan.org/tx/0x5936515cc428ce9d66396d995b490f059da4152c182e1e8f42dc7ce6a38fd278)
* These ALB are reserved as a treasury and vested team allocation, and aren't currently part of circulating supply. The timelock lasts forever, as it introduces a 7 day delay to any action. Any movement can be tracked and will be announced by the team.

\
\
DEX Contracts:

* Factory: [https://basescan.org/address/0x3e84d913803b02a4a7f027165e8ca42c14c0fde7](https://basescan.org/address/0x3e84d913803b02a4a7f027165e8ca42c14c0fde7)
* Router: [https://basescan.org/address/0x8c1A3cF8f83074169FE5D7aD50B978e1cD6b37c7](https://basescan.org/address/0x8c1A3cF8f83074169FE5D7aD50B978e1cD6b37c7)
* Farm Contract: [https://basescan.org/address/0x52eaecac2402633d98b95213d0b473e069d86590](https://basescan.org/address/0x52eaecac2402633d98b95213d0b473e069d86590)
  * The contract is controlled by a special selective timelock proxy at [https://basescan.org/address/0x16f1F80654F2FEA97293321675907CFA2e23e4fB](https://basescan.org/address/0x16f1F80654F2FEA97293321675907CFA2e23e4fB)
  * Changing owner, changing ALB emission rate and other privileged functions are timelocked
  * Adding new farms or changing settings on existing ones is allowed without timelocks to ensure fast response to the market
  * Deposit fees are currently set to zero and cannot be increased once the farm is live.
* Area 51 Router: [0x837d9B4139dFbAc869b2c67771730bC822863376](https://basescan.org/address/0x3485F8E155973cC247CBEa9E77C0dBBB4BBb79E7)
* Area 51 Factory: [0x2d5dd5fa7B8a1BFBDbB0916B42280208Ee6DE51e](https://basescan.org/address/0x2d5dd5fa7B8a1BFBDbB0916B42280208Ee6DE51e)

esALB Contracts:

* esALB: [https://basescan.org/address/0xe1afc637f41e05efe08d55296a2ccff0072a4587](https://basescan.org/address/0xe1afc637f41e05efe08d55296a2ccff0072a4587)
* config.esMasterAddress: [https://basescan.org/address/0xd3968a4a07d64c6e16982d45191b9a09a261ec88](https://basescan.org/address/0xd3968a4a07d64c6e16982d45191b9a09a261ec88)
* esALB-ETH pair: [https://basescan.org/address/0x176ca19007b1e2c9d85b8ecd68f89bb7f8a208f0](https://basescan.org/address/0x176ca19007b1e2c9d85b8ecd68f89bb7f8a208f0)
