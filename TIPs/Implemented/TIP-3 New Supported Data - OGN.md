---
TIP: 3
Title: New Supported Data - OGN
Discussions-to: https://github.com/tellor-io/TIPs/issues/3
Status: Implemented
Category: Off-chain-New Data
Author: <a @themandalore>,Nick (@themandalore)>
Created: 10-29-2020
---

# TIP-3 New Supported Data - OGN

### TLDR

Add the Origin Protocol (OGN) price to list of supported Tellor prices.  



# Proposal

In the contract, add another request ID

In the miner code, add as a subsequent PSR and the following API's in the indexes.json file. 



'''
	"OGN/USD": [
		"json(https://api.coingecko.com/api/v3/simple/price?ids=origin-protocol&vs_currencies=usd).origin-protocol.usd",
		"json(https://min-api.cryptocompare.com/data/price?fsym=OGN&tsyms=USD).USD",
		"json(https://api.binance.com/api/v1/klines?symbol=OGNUSDT&interval=1d&limit=1).0.4"
	],


'''

### Implementation
This update was implemented on the Tellor Miner Release v5.2.0: [https://github.com/tellor-io/TellorMiner/releases/tag/v5.2.0](https://github.com/tellor-io/TellorMiner/releases/tag/v5.2.0)