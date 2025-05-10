
Tackling scalability at the L1 level is designing or redesigning your protocol to improve throughput, latency and finality.

## Choice of Consensus Mechanism

Using a voting approach such as in BFT can have a negative impact on scalability. This is caused by the increase in the amount of messages being passed as the number of validators increases. Therefore chains adopting a BFT based approach tend to use additional mechanisms to offset this.

On Ethereum validators form committees and votes are aggregated by committee.

## Reducing transaction broadcasts

Solana moved away from using a gossip protocol to get transactions to the relevant parties. They reasoned that only the leader (block producer) needs to receive transactions, so on receiving transactions, nodes will send them to the leader rather than other nodes.

## Parallel processing of transactions

In Ethereum transactions are ordered by the block producer and then executed sequentially. This has the benefit of simplicity, but leads to

- MEV
- Poor horizontal scaling

More recent chains such as Solana / Aptos / Sui allow parallel processing of transactions. They rely on an understanding of what areas of state will be changed by a transaction, and therefore a dependency among transactions. From this they can allow 'non dependent' transactions to be processed in parallel.

## Sharding

Ethereum plans to introduce 64 new shard chains, to spread the network load.![b7oUD58.png](https://i.imgur.com/b7oUD58.png) Vitalik's [overview](https://vitalik.eth.limo/general/2021/04/07/sharding.html) [Introduction](https://medium.com/@icebearhww/ethereum-sharding-and-finality-65248951f649)

![](https://i.imgur.com/b7oUD58.png)

### Introduction of Sharding

Vitalik sees 3 options

- Shards remain as data depots
- A subset of the 64 shards will allow smart contracts
- Wait until increased use of ZKPs allows private transactions

Points from an [article](https://vitalik.eth.limo/general/2021/05/23/scaling.html) by Vitalik

There are three key limitations to a full node's ability to process a large number of transactions:

- **Computing power**: what % of the CPU can we safely demand to run a node?
- **Bandwidth**: given the realities of current internet connections, how many _bytes_ can a block contain?
- **Storage**: how many gigabytes on disk can we require users to store? Also, how quickly must it be readable? (ie. is HDD okay or do we need SSD)

Many of the scalability approaches we see concentrate on the issue of computing power and how that can be made sufficient.
