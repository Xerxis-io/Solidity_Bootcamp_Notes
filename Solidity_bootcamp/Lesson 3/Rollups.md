### ZKP or validity Rollups

These rollups rely on a proof of the correctness of the execution that produces the rollup block state transition being supplied to a validator contract on L1. The state transition on L2 will not be regarded as valid unless this proof has been validated. Although we use a zero knowledge proof, the zero knowledge aspect is usually ignored, the inputs and data involved is usually public, the focus is on the correctness of computation. For this reason some people prefer the term validity proof.

### Optimistic Rollups

The name Optimistic Rollups originates from how the solution works. 'Optimistic' is used because aggregators publish only the bare minimum information needed with no proofs, assuming the aggregators run without commiting frauds, and only providing proofs in case of fraud. 'Rollups' is used because transactions are commited to main chain in bundles (that is, they are rolled-up).

![](https://i.imgur.com/VnpCTDD.png)

See this [article](https://www.alchemy.com/overviews/validity-proof-vs-fraud-proof#:~:text=What%20is%20a%20validity%20proof,information%20shared%20between%20the%20two.) for further discussion of the differences between these types of rollups.