# Multi-Chain

HashKey DID is a decentralized identity that supports multiple chains. The synchronization protocol is implemented through the [LayerZero protocol](contract-api-reference/layerzero.md). However, some chains are not yet supported by LayerZero, so we use middleware that we have developed to synchronize the DID with those chains.



### 1. Chains

The chains that DID supports registration and data synchronization are:

* Ethereum
* Polygon
* Moonbeam
* PlatON



### 2. Gas Fee

Users need to pay gas fees when sync their DIDs. Because the fluctuation of gas fees is unstable, we will charge 10-20% more than real-time gas fees on each chain, to ensure the success of the transaction.

When users sync information to a chain with an existing DID, it is equivalent to the users initiating a transaction directly on the target chain, rather than using a cross-chain protocol.





