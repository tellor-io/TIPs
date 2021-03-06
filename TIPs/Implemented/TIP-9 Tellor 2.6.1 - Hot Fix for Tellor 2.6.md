---
TIP: 9
Title: Tellor 2.6.1 - Hot Fix for Tellor 2.6
Discussions-to: https://github.com/tellor-io/TIPs/issues/15
Status: Implemented
Category: On-chain > Security
Author: JG Carvalho (@jgcarv)
Created: 2021-02-03
---

# TIP-9: HotFix for Tellor 2.6

### TLDR
* Fix a bug that allows bypassing the nonce verification for values submitted
* Adjust difficulty to 1000000000 since the difficulty raised significantly from this bug
* Update an event that was being emitted with incorrect values


## Proposal
Remove the rounding to the minute when verifying if the nonce is correct.  Before v2.6, when new values were submitted the contract rounded them to the nearest minute, which is a feature that comes from the first version of Tellor contracts. In the last upgrade we opted to remove this rounding, as it was affecting the difficulty adjustments calculations. Due to an oversight, there's still the `verifyNonce` function that uses the passed time as if it were still rounded. Also, adjust the difficulty to 1000000000 since the difficulty raised significantly from this bug and update an event that was being emitted with incorrect values.


Voting period goes for 7 days and it began: 2/7/2021

## Fix
[https://github.com/tellor-io/TellorCore/tree/fix](https://github.com/tellor-io/TellorCore/tree/fix)


## Implementation

V2.6 was implemented through a community vote. However, Tellor had to be updated shorlty after with a fork because the old Tellor system was frozen. More information on this is detailed on the post morten article published here: [Tellor's V1 Post-mortem](https://medium.com/tellor/tellor-token-v1-da0d485af48e)