# V3 Contracts

Alien Base V3 is built using a core of stock Uniswap V3 and the Bunni liquidity management protocol. The Core contracts were extensively audited by their creators and were not changed.

Some periphery contracts like SmartRouter (forked from Pancake) and BunniZap were lightly adapted for Alien Base.

Below are the core contracts used for Alien Base V3:

| Type               | Address                                                                                                                                                      | Description                                    |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------- |
| Factory            | [0x0Fd83557b2be93617c9C1C1B6fd549401C74558C](https://basescan.org/address/0x0Fd83557b2be93617c9C1C1B6fd549401C74558C)                                        | Uniswap V3 Factory                             |
| SmartRouter        | [https://basescan.org/address/0xB20C411FC84FBB27e78608C24d0056D974ea9411#code](https://basescan.org/address/0xB20C411FC84FBB27e78608C24d0056D974ea9411#code) | Combined V2, Stable and V3 router              |
| NFTPositionManager | [https://basescan.org/address/0xB7996D1ECD07fB227e8DcA8CD5214bDfb04534E5](https://basescan.org/address/0xB7996D1ECD07fB227e8DcA8CD5214bDfb04534E5)           | Position manager contract for raw V3 positions |
| BunniHub           | [https://basescan.org/address/0xDC53487e2a6eF468260Bc938F645f84caaccAC6F](https://basescan.org/address/0xDC53487e2a6eF468260Bc938F645f84caaccAC6F)           | Position manager for preset farmable ranges    |
| BunniZap           | [https://basescan.org/address/0x6947DA282E447a2e9d65ff00aAf80efB5116D75d](https://basescan.org/address/0x6947DA282E447a2e9d65ff00aAf80efB5116D75d)           | Bunni helper contract for WETH and more        |
| BunniToken         | [https://basescan.org/address/0x053d11735f501199ec64a125498f29ed453d27a4](https://basescan.org/address/0x053d11735f501199ec64a125498f29ed453d27a4#code)      | Sample Bunni LP token                          |
