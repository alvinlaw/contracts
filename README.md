
# Bancor Protocol Contracts v0.5 (beta)

## Overview

Bancor is a decentralized liquidity protocol that provides tokens with constant liquidity. The protocol is made up of a series of smart contracts which are designed to pool liquidity and perform non-custodial token-to-token conversions in a single transaction. More than 150 tokens are integrated with the Bancor Protocol, including ETH, EOS, DAI, IQ, PEOS & more. 

* Join the [Bancor Developers Telegram group](https://t.me/BancorDevelopers) or the [Bancor Protocol Telegram group](https://t.me/bancor)
* Check out the [Bancor Blog](https://blog.bancor.network/) 
* Read the Bancor Protocol [Whitepaper](https://storage.googleapis.com/website-bancor/2018/04/01ba8253-bancor_protocol_whitepaper_en.pdf)
* Visit the [Bancor Web App](https://www.bancor.network/communities/5a780b3a287443a5cdea2477?utm_source=social&utm_medium=github&utm_content=readme)

## How Bancor Works

Token conversions via the Bancor Protocol are executed against on-chain liquidity pools known as “Bancor Relays”. Each Relay holds reserves of both BNT (Bancor’s Network Token) and a base token (which could be any ERC20 or EOS-based token, with more blockchains to come). For instance, the base token for the ‘DAIBNT’ Relay is DAI.

A Relay’s reserves receive and dispense tokens in order to fulfill trades and are autonomously rebalanced to determine prices. Selling BNT for the base token increases the size of the BNT reserve and decreases the size of the base token’s reserve. This shifts the reserve ratio, increasing the base token's price relative to BNT for subsequent transactions. The larger a trade relative to the total size of the reserves, the more price slippage will occur. 

Since BNT is a common pair for all Relays, it can be used as an intermediary allowing direct token-token trades in a single transaction, including across different blockchains. Notably, traders never need to hold BNT to perform conversions via Bancor Protocol.

## Providing Liquidity on Bancor

Anyone can become a liquidity provider to a Relay and contribute to its reserves. This is different than buying tokens on Bancor. It requires staking tokens in a Relay. Users can stake their tokens in a Relay by buying “Relay Tokens” on bancor.network, or through any third-party liquidity portal built atop the Bancor Protocol. Relay Tokens can be sold at any time to withdraw a proportional share of the Relay’s liquidity.    

Each time a Relay processes a conversion, a small liquidity provider fee (usually 0.1-0.3%) is taken out of each trade and deposited into the Relay’s reserves. These fees function as an incentive for liquidity providers who can withdraw their proportional share of the reserves including the accumulated fees. The larger a Relay’s reserves, the lower the slippage costs incurred by traders transacting with the Relay, driving more conversion volume and, in turn, more fees for liquidity providers. 

Currently, whoever initiates the Relay determines its fees, while in the future, liquidity providers will be able to vote on the Relay’s fee. Bancor takes no platform fee from trades.

## Upgradeability

All smart contract functions are public and all upgrades are opt-in. If significant improvements are made to the system a new version will be released. Token owners can choose between moving to the new system or staying in the old one. If possible, new versions will be backwards compatible and able to trade with the old versions.

## Language

A “Smart Token” refers to tokens which utilize reserves to automate trading, including “Liquid Tokens” (one reserve), “Relay Tokens” (two reserves) and “Array Tokens” (three or more reserves). See Section 6 of the [Bancor Whitepaper](https://storage.googleapis.com/website-bancor/2018/04/01ba8253-bancor_protocol_whitepaper_en.pdf) (“Smart Token Configurations”) for more details.

The terms “reserves” and “connectors” have the same meaning throughout Bancor’s smart contract code and documentation. “Reserve ratio” and “connector weight” are also used interchangeably. “Connector balance” refers to the token inventories held in a Smart Token’s reserve.

## Warning

Bancor is a work in progress. Make sure you understand the risks before using it.

## Testing

### Prerequisites

* node 10.16.0
* npm 6.9.0
* python 3.7.3
* web3.py 4.9.2

### Installation

* `npm install`

### Verification

* Verifying all the contracts:
  * `npm test 1` (quick testing)
  * `npm test 2` (full coverage)
* [Verifying the BancorFormula contract](solidity/python/README.md)

### [Utilities](solidity/utils/README.md)

### Deployed Kovan Testnet

contractRegistry deployed at 0x1757a6463fE7F4c4bB33a3Fff10D6a5e152E80e2
contractFeatures deployed at 0x35CDa570C4504B1464F43F6B59c80C3a77d9e61A
bancorFormula deployed at 0xC3607d293f3cdEc4A6F75a7B787ED414630B1B6d
bancorNetwork deployed at 0x5a8a71c5cE3824c62fEFF0042f2CdCDe023c0a33
bancorNetworkPathFinder deployed at 0xD547E6cBB8A1be5e961AA9bdEEBF8B34e9D69BC6
bancorConverterRegistry deployed at 0x3E200b0950fb26877e3c01581CAfe609Fb912651
bancorConverterRegistryData deployed at 0xDD023d4BD29eE326827367cDC0ed8870a52643CE
etherToken deployed at 0x05708921f9AC850d05db2645299C8b3708539763
smartToken0 deployed at 0x1996702B6D7a795C9B5b4c64E6C51507951B0374
smartToken1 deployed at 0x5363Bb40D1BD49f309e97c4f3af030D2C64cf12E
smartToken2 deployed at 0x3A07FFdA6a14feCD6f34D11615196BD4704817b8
smartToken3 deployed at 0x9b048416310eF13359AA1c1968FC0bb33E677906
smartToken4 deployed at 0xE85656eB4a35159d4118cf3248560eA53817aE9C
erc20TokenA deployed at 0x729B85Fbe194073F5857d5560C61c2923fC7149c
erc20TokenB deployed at 0xcd2Ee44229AD23002aBC63387AB949CF21451417
bancorConverter1 deployed at 0x324A4a8ea05052B2fC7767E07095b03BDfaE41b4
bancorConverter2 deployed at 0x8d09Ba659Da77Cb23e96aD38Ae2e9034dAfF0087
bancorConverter3 deployed at 0x5bF6CEBBCE4e6cD842103dC940849181eACB9e49
bancorConverter4 deployed at 0xC92A9b05B19EBab9E9CD7D7b83eB187fF1D1dF24

## Collaborators

* **[Yudi Levi](https://github.com/yudilevi)**
* **[Barak Manos](https://github.com/barakman)**
* **[Ilana Pinhas](https://github.com/ilanapi)**
* **[David Benchimol](https://github.com/davidbancor)**
* **[Or Dadosh](https://github.com/ordd)**
* **[Martin Holst Swende](https://github.com/holiman)**

## License

Bancor Protocol is open source and distributed under the Apache License v2.0
