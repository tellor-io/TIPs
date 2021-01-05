---
TIP: TIP-2
Title: Tellor V2.5
Discussions-to: https://github.com/tellor-io/TIPs/issues/2
Status: Implemented
Category: General
Author: Tellor Team POCs Brenda (@brendaloya) , Nick (@themandalore)
Created: 2020-10-09
---


# TIP-2 Tellor V2.5

### TLDR

* Staking reduced from 1000 TRB to 500 TRB 
* Current miner reward changed from 1 TRB + tips/2 to: 

![RewardsUpdate](https://github.com/tellor-io/TIPs/blob/main/TIPs/public/rewardsUpdate.jpg)

## Proposal
There are two key features of this upgrade, chosen specifically to be non-controversial so as to get a vote through.  They are:

### Reduced staking amount
The miners staking amount has been decreased from 1000 to 500 TRB. Decreasing the stake amount incentivizes miners to join the network. This change complements an update done on Tellor V2 where miners are now only allowed to "win" once every 15 minutes to incentivize growth in the miner network.

### Reward is now a function of blocktime
Instead of miners getting paid a fixed reward each block, the mining reward will be based on the time since the last block.  The current reward is 1 TRB per miner per Tellor block with the difficulty target at 5 minutes.  The problem is that if gas costs are high enough that 1TRB + tips is less than the cost, no miners submit and the network stalls.  Users can tip extra to miners, but this is a heavily manual process and forces even more txns on the already clogged network. The solution is to make the reward based upon the time since the last Tellor block.  Now if a block is mined at 5 minutes, the reward will be 1 TRB per miner.  If the block is mined at 10 minutes, the reward will be 2 TRB per miner.  

This change will allow the Tellor network to have a more predictable inflation rate, to continue to add data (even if it is at a slower rate) during times of high gas costs, and for the parties that cannot tip exorbitant amounts, the TRB network will still continue to function.  

### Link to repo with code

[https://github.com/tellor-io/TellorCore/tree/dev](https://github.com/tellor-io/TellorCore/tree/dev) 


### Outcome 

* The vote passed (the voting period ended on 10/23/2020)
* 18 % of total supply voted 
* The proposed Tellor contract was implemented on 10/25/2020

### Link to press release

[https://medium.com/tellor/the-tribe-has-spoken-e25b05949ffe](https://medium.com/tellor/the-tribe-has-spoken-e25b05949ffe) 

