Generally speaking, transactions are submitted to these layer 2 nodes instead of being submitted directly to layer 1 (Mainnet). For some solutions the layer 2 instance then batches them into groups before anchoring them to layer 1, after which they are secured by layer 1 and cannot be altered. A specific layer 2 instance may be open and shared by many applications, or may be deployed by one project and dedicated to supporting only their application.

### Layer 2 Solutions on Ethereum
[L2BEAT - The state of the layer two ecosystem](https://l2beat.com/scaling/summary)

![](https://solidity.bootcampnotes.xyz/img/Ethereum-Layer-2.png)

### [Rollups](./Rollups.md)

Rollups are solutions that have

- transaction execution outside layer 1
- data or proof of transactions is on layer 1
- a rollup smart contract in layer 1 that can enforce correct transaction execution on layer 2 by using the transaction data on layer 1

The main chain holds funds and commitments to the side chains The side chain holds state and performs execution There needs to be some proof, either a fraud proof (optimistic) or a validity proof (zk)

Rollups require "operators" to stake a bond in the rollup contract. This incentivises operators to verify and execute transactions correctly.

There are currently 2 types of rollups

- Zero Knowledge Proof rollups
- Optimistic rollups
