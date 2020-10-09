---
TIP: TIP-2
Title: Tellor V2.5
Discussions-to: https://github.com/tellor-io/TIPs/issues/2
Status: Draft
Category: General
Author: Tellor Team POCs Brenda (@brendaloya) , Nick (@themandalore)
Created: 2020-10-09
---


# TIP-2 Tellor V2.5

### TLDR

* Staking reduced from 1000 TRB to 500 TRB 
* Current miner reward changed fron 1 TRB + tips to 1 TRB + tips + timeSinceLastMineValue/5Min


## Proposal
There are two key features of this upgrade, chosen specifically to be non-controversial so as to get a vote through.  They are:

### Reduced stake
Move from 1000 to 500 TRB 

Decreasing the stake amount attempts to incentivise more miners to join the network. This change complements an update done on Tellor V2 where miners are now only allowed to "win" once every 15 minutes to incentivize growth in the miner network.

### Reward is now a function of blocktime

Instead of miners getting paid a fixed reward each block, the mining reward will be based on the time since the last block.  The current reward is 1 TRB per miner per Tellor block with the difficulty target at 5 minutes.  The problem is that if gas costs are high enough that 1TRB + tips is less than the cost, no miners submit and the network stalls.  Users can tip extra to miners, but this is a heavily manual process and forces even more txns on the already clogged network. The solution is to make the reward based upon the time since the last Tellor block.  Now if a block is mined at 5 minutes, the reward will be 1 TRB per miner.  If the block is mined at 10 minutes, the reward will be 2 TRB per miner.  
Now the Tellor network will have a more predictable inflation rate, move slower during times of high gas costs, but even for the parties that cannot tip exorbitant amounts, the TRB network will still continue to function.  

