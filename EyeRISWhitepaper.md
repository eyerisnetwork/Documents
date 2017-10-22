# EyeRIS White Paper (work in progress)

**Date**

**Abstract**: The EyeRIS software provides a novel approach for securing a decentralized ledger network capable of running smart contracts and dApps through the use of a new consensus algorithm: PoUTR (Proof of User Tick Rate). This algorithm uses real time online videogame server connections from the player side to cryptographically secure transactions between network participants. The resulting effect is that no additional network security infrastructure is needed as players can secure transactions passively through their activity, the architecture allows for almost instant decentralization from deployment given the nature of the algorithm and the amount of online players at any given time, user fees are significantly reduced as a result of the distributed nodes and competition for fees, and geographical decentralization is possible, also enabling fast deployment of dApps at a global scale.

# Context

The first distributed ledger protocol was released in 2008 in the form of Bitcoin, using a Proof of Work (PoW) algorithm where nodes in the network (the "miners") must solve computational problems and rewarded with bitcoins. As bitcoin development and adoption increased over the years, other developers have attempted to improve on the technology in order to increase the scalability, enable a wider range of applications and services on an underlying blockchain, and prevent centralization. The existing bitcoin blockchain is limited in the applications it can run in the present moment, it can be subject to costly fees, and the type of PoW algorithm it uses has lead to the centralization of its network securing infrastructure, both economically and geographically, preventing far-reaching adoption.

An additional problem with the bitcoin blockchain and other alternative blockchain networks is the requirement for the dedicated use of computing power and energy in other to ensure network security. A blockchain network which could run from existing computational and energy use would thus be superior from a resource-conserving point of view, an essential point in the scalability of the network to a potentially global user base.

# Consensus Algorithm

## Rationale

The decision behind developing a new consensus algorithm based on online gaming connection speeds as a Proof of Stake (PoS) equivalent serves precisely to take advantage of existing infrastructure in order to reduce energy usage and increase the starting levels of decentralization. PoUTR would also prevent the incentive for accumulation from PoS consensus algorithms, improving the gini index of the EyeRIS cryptocurrency.

## Proof of User Tick Rate

Under the PoUTR algorithm, blocks producers are chosen by surveying players running the EyeRIS node wallet, which monitors players' tick rate in their current online game and assign a stake to each player sending updates to the server at a frequency between 50Hz and 250Hz (a common range of frequencies for competitive online games). Each staked player is then added to a time-based list/queue to participate in the block production. Such time-based list/queue is updated in real-time with the player tick rate frequency in order to confirm the player is, indeed, playing. After having participated in the production of a block, the staked player has its stake removed and, if still connected to the network and with a tick rate between 50-250Hz, will be placed in the bottom of the list/queue where its timestamp will increase once again. As the players produce blocks, they move to the bottom of the list/queue and newer players move up. This list is maintained and updated in all nodes in real time.

Thus, the EyeRIS network enables block production to occurr every 1 - 5 seconds, with one player to be authorized by the time hierarchy to produce a block at any moment. If player network interruption occurrs, the next player in the list is selected (with a time delay of 10ms) until one player can keep a stable connection during the whole block production event. It can be expected that the time-based queue would be a long one given the sheer amount of connected players at any given time. Block production will therefore happen continuously rather than in rounds, with a dynamic fluctuation in time based on the number of connected players.

During normal operation the blockchain will not experience any forks since there is a time-based hierarchy to compete for the next block, and each future block producer is already in line for the longest blockchain produced by the previous block producer. As a consequence, future network updates will require temporary interruptions, affecting transactions and dApps, while the first player running the new software is awarded the production of the new forked block.

[EyeRIS PoUTR Logic](https://github.com/eyerisnetwork/Documents/blob/master/eyeris_poutrlogic.png)

## Wallet

The EyeRIS node wallet will be able to anonymously monitor internet traffic frequency by the player and correlate it with installed games selected by the user. Players wishing to contribute will run a node wallet (also known as a full wallet), while users interested only in performing transactions or running higher applications will use a light wallet (compatible with mobile devices).

To resist network stops due to any given game maintenance issues, the EyeRIS node wallet will be compatible will all PC online games through a simple player set-up selection tool, which allows the player to select which .exe files the wallet must correlate with the monitored internet traffic. This way, other players in other online games will be able to contribute to the block production if a specific game experiences network issues, is discontinued, or is being updated. 

## Transactions

With a PoUTR algorith, the EyeRIS network can confirm transactions with speeds below 5 seconds, assuming a sufficient queue of active staking players (greater by a factor of 5 than the number of blocks waiting to be confirmed). As transactions will contain the hash of the most recent block, this will prevent a transaction replay on forks excluding the referenced block.

# Accounts

When an user creates an account in the EyeRIS network, there will be an option to generate a unique human readable name containing 32 characters in length. Each user account will require a minimum amount of funds in order to use the network at any give time. 
