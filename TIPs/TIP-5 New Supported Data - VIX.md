---
TIP: 5
Title: New Supported Data - VIX
Discussions-to: https://github.com/tellor-io/TIPs/issues/5
Status: Implemented
Category: Off-chain-New Data
Author: <a @themandalore>,Nick (@themandalore)>
Created: 11/3/2020
---

# TIP-5 New Supported Data - VIX

### TLDR

Add the CBOE VIX price to list of supported Tellor prices.  



# Proposal

In the contract, add another request ID

In the miner code, add as a subsequent PSR and the following API's in the indexes.json file. 

Note:  This will likely require the additon of permissioned APIs 

We need the front month close on the VIX.  An example would be here: https://www.quandl.com/data/CHRIS/CBOE_VX1-S-P-500-Volatility-Index-VIX-Futures-Continuous-Contract-1-VX1-Front-Month

A PR will be coming in the miner to handle these apikeys in your config file

'''
	"VIX": [
		"json(https://www.quandl.com/api/v3/datasets/CHRIS/CBOE_VX1.json?api_key=4enfkxxxxxxxxxxxxxxx).dataset.data.0.4"
	],

'''

### Implementation
This update was implemented on the Tellor Miner Release v5.2.0: [https://github.com/tellor-io/TellorMiner/releases/tag/v5.2.0](https://github.com/tellor-io/TellorMiner/releases/tag/v5.2.0)