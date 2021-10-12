---
TIP: TIP 13
Title: New Supported Data - 7 day TWAP of gas prices
Status: Draft
Category: Off-chain-New Data, Telliot
Author: Brenda Loya (@brendaloya), Apollo
Created: 2021-02-02
---

# TIP 13 - New Supported Data - 7 day TWAP of gas prices

### TLDR

Add 7 day TWAP of Mainnet Ethereum gas prices. 


# Proposal

To provide a week long average gas price to the network.  Etherscan has an API for average gas price by day: https://docs.etherscan.io/api-endpoints/gas-tracker  Anyblocks as well has an API you can use: https://www.anyblockanalytics.com/blog/historical-ethereum-gas-price-analysis/ 

Or you can alternatively calculate it the hard way by looking back at what gas prices people paid in each block (getBlock and go through txns).  