---
TIP: 11
Title: New Supported Data - ETH/JPY
Discussions-to: https://github.com/tellor-io/TIPs/issues/18
Status: Draft
Category: Off-chain-New Data
Author: Yamato Protocol Team 0xsomewherecat (@0xsomewherecat), Pre-draft review by Mr. Kernell (@tkernell)
Created: 28/7/2021
---

# TIP-11 New Supported Data - ETH/JPY

### TLDR

Add the ETH/JPY price to list of supported Tellor prices.

JPY is among the top-volume currencies in the world. JPY stablecoin services (both Daap and companies) are just emerging. We believe that ETH/JPY price on the trusted Tellor protocol will be valuable addition for the ecosystem.

# Proposal

In the contract, add another request ID.

In the miner code, add as a subsequent PSR and the following API's in the indexes.json file.
'' "ETH/JPY": [ "json(https://api.coingecko.com/api/v3/simple/price?ids=ethereum&vs_currencies=jpy&include_last_updated_at=true).ethereum.jpy","json(https://api.bitflyer.com/v1/getticker?product_code=ETH_JPY).ltp","json(https://api-pub.bitfinex.com/v2/ticker/tETHJPY)[6]"]"

Note: This will not require the addition of permissioned APIs, as these are all public endpoints.

### Price source summary (inclusive of the gist for each price source)
https://docs.google.com/spreadsheets/d/1lVE4gNNeRZiOsOjRl3u0jBO6u5szxT5ZXDlhsh9AbRA/edit#gid=775297008

### Price source description
1. CoinGecko: Proposed as the primary source as it is an aggregated price from various DEXes & CEXes, considered a fairly stable & objective feed.
1. Bitflyer: Proposed as the secondary source as it is the biggest CEX in Japan offering the ETH/JPY pair directly, considered a good indication of liquidity.
1. Bitfinex: Proposed as the tertiary source as it is (probably) the biggest CEX outside Japan offering the ETH/JPY pair directly, considered a good off-shore feed.
