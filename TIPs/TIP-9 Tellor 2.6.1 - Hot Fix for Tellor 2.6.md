---
TIP: 9
Title: Tellor 2.6.1 - Hot Fix for Tellor 2.6
Discussions-to: None
Status: Draft
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




