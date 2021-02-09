---
TIP: TIP 10
Title: New Supported Data - TWAP with Custom Volatility Index
Discussions-to: https://github.com/tellor-io/TIPs/issues/14
Status: Draft
Category: Off-chain-New Data, Telliot
Author: Brenda Loya (@brendaloya), Apollo
Created: 2021-02-02
---

# TIP 10 - New Supported Data - TWAP with Custom Volatility Index

### TLDR

Add TWAP with custom volatility index that will be requested on a quarterly basis. The volatility index components include seven top GDPs, seven highly used fiat currencies, and seven highly traded commodities/metals specified by Apollo. 


# Proposal

To provide a TWAP with a custom volatility index, On a quarterly basis. This will initially be a manual feed in and a new PSR (id 59) in Telliot.

Each specified component is weighted according to the volatility index as specified below:

Component 1 = C1
Component 2 = C2 …

Volatility Factor (VF) of C1:

{|price(C1)annual max - price(C1)annual min| * (price(C1)mean)-1} + {STDev(C1)}

Volatility Index (VI) of C1:

VF(C1) / Σ (VF(C1)…VF(C21)

Weighted Price (WP) of (C1) = VI(C1) * TWAP(C1)/Initial Price(C1)

Initial PEG: Σ WP(C1) + WP(C2) + … WP(C21) = $1.00

The PEG changes according to the weight of each asset since their weight is affected by the TWAP. 

The index includes the following components: 

**Component**|**API**
:-----:|:-----:
GDP: USA|https://data.worldbank.org/country/united-states?view
GDP: China|https://data.worldbank.org/country/china?view
GDP: Germany|https://data.worldbank.org/country/germany?view
GDP: Japan|https://data.worldbank.org/country/japan?view
GDP: India|https://data.worldbank.org/country/india?view
GDP: UK|https://data.worldbank.org/country/united-kingdom?view
GDP: France|https://data.worldbank.org/country/france?view
Fiat: CNY|https://www.federalreserve.gov/releases/h10/current/
Fiat: USD|https://www.federalreserve.gov/releases/h10/current/
Fiat: EUR|https://www.federalreserve.gov/releases/h10/current/
Fiat: JPY|https://www.federalreserve.gov/releases/h10/current/
Fiat: GBP|https://www.federalreserve.gov/releases/h10/current/
Fiat: KRW|https://www.federalreserve.gov/releases/h10/current/
Fiat: INR|https://www.federalreserve.gov/releases/h10/current/
Crude Oil|https://www.eia.gov/dnav/pet/pet\_pri\_spt\_s1\_d.htm
Natural Gas|https://www.eia.gov/dnav/ng/ng\_pri\_sum\_dcu\_nus\_m.htm
Gold|https://markets.businessinsider.com/commodities/gold-price
Silver|https://markets.businessinsider.com/commodities/silver-price
Copper|https://markets.businessinsider.com/commodities/copper-price
Coffee|https://markets.businessinsider.com/commodities/coffee-price
Wheat|https://markets.businessinsider.com/commodities/wheat-price

Link to example:
Work in progress - will add link to example