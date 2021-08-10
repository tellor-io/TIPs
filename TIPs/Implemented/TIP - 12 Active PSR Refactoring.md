---
TIP: 12
Title: Active PSR Refactoring
Discussions-to: None
Status: Implemented
Category: Off-chain > Security
Author: themandalore
Created: 2021-08-09
---

# TIP-12: Active PSR Refactoring

### TLDR
* Only support ID's that are actively being used. 
* A simple request / TIP can turn them back on to active
* Only active disputes will be allowed to be disputed.  If disputes happen on non-active disputes, they will be voted down
* In Tellor X, the plan is to have them voted as invalid
* Use this sheet to manage: https://docs.google.com/spreadsheets/d/1BK7Cs0K2W-bRaNpuvzFbVX50CgjXH7k-HKAuuWxTiW8/edit#gid=0

## Proposal
Add a list of ID's that are "active" which means they are secured by the disputing process.  This is an off-chain coordination to better protect miners and disputers from the ambiguity involved in some sparsely used PSR ID's. 


# Motivation
Recent problems have arisen where a PSR that is not used is found to have an error (e.g. an API is discontinued).  Some one will tip the ID to bring it on-chain and dispute parties who place data on-chain
 * The mining of Tellor data should not be a game about finding and exploiting other miners using outdated API's.  
 * This is especially true when the PSR's are not used.  
 * Since Tellor (the smart contracts), have no way of removing an ID, it is necessary to have this coordination off-chain. 

# Risk Register
This section includes risks identified should this proposal be implemented:
| Description | Mitigating Factors |
|-------------|--------------------|
|There is a risk that miners will start tipping and mining only invalid ones so they can get rewards without risk. | An active tipping economy will be necessary, and miners will need to know that disputes can still happen (or even turned on) if the system is not working as intended |

