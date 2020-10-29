---
TIP: 3
Title: New Supported Data - WAVES
Discussions-to: https://github.com/tellor-io/TIPs/issues/4
Status: Draft
Category: Off-chain-New Data
Author: <a @themandalore>,Nick (@themandalore)>
Created: 10-29-2020
---

# TIP-4 New Supported Data - WAVES

### TLDR

Add WAVES price to list of supported Tellor prices.  



# Proposal

In the contract, add another request ID

In the miner code, add as a subsequent PSR and the following API's in the indexes.json file. 



'''
	"WAVES/USD": [
		"json(https://api.coingecko.com/api/v3/simple/price?ids=waves&vs_currencies=usd).waves.usd",
		"json(https://min-api.cryptocompare.com/data/price?fsym=WAVES&tsyms=USD).USD",
		"json(https://api.binance.com/api/v1/klines?symbol=WAVESUSDT&interval=1d&limit=1).0.4"
	],


'''