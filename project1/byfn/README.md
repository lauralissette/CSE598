# Hyperledger Fabric Network Setup

The official documentation for Hyperledger Fabric can be found [here](https://hyperledger-fabric.readthedocs.io/en/release-1.3/).

Also the official code for hyperledger fabric can be found [here](https://github.com/hyperledger/fabric) on github.

Let's begin with clearing out some misconceptions about Hyperledger:

- Hyperledger is based on blockchain technology but it is not a cryptocurrency. You can create cryptocurrency with hyperledger if you want to.

- Hyperledger uses a completely different consensus algorithm that makes mining unnecessary. Just to be clear **there is no mining in Hyperledger**.

- Although there is no mining hyperledger still manages to have the cryptographic reliability that other blockchain solutions have. Due to this tradeoff in mining, higher throughput can be achieved using Hyperledger.

- Hyperledger is distributed by design, since there is no single place of failure and there are no data troves.

- Hyperledger although a permissioned blockchain can be made as public as we want. The only condition is that any two parties interacting must have some kind of network visibility.

- A 51% attack is not applicable to hyperledger since there is no concept of mining and computation power.

How hyperledger establishes trust:
----------------------

- Let's say there are two parties, A and B, who do not trust each other with business transactions and data. Hence they maintain their own servers to store data.

- Now if there's a settlement to be processed, that might be tedious since the two data servers might have different schemas and technologies used. Hence settlements would take very long to complete.

- Now imagine a supply chain with 10 parties and each of them communicating with each other in different ways. This is very hard to manage.

- The most commonly used approach is using a trusted third party for data integrity, processing, and security.

- But this approach might create more problems than it solves.

- First of all, this approach would cost a lot of money. It's very hard to find a common party that everyone trusts, especially in the case of international transactions.

- The biggest problem is that within this third party opeate real humans. There is a possibility of someone tampering with the data. Also this altered data will be very hard to track.

- The solution that hyperledger offers is that all parties run a infrastructure such that that it's replicated on multiple sites. If there is an anomaly in the data, it will be visible to everyone on the network. If any hacker manages to update all ledgers at the same time, still the data will fail cryptographic verification (smart contract or chaincode-based verification).

Three main components for Hyperledger Fabric:
---------------------
1. Fabric-CA
2. Fabric Peer
3. Fabric Orderer

## 1. Fabric Certificate Authority:
--------------------
- Every single operation that is executed in hyperledger fabric must be signed cryptographically with a certificate.
- These certificates can be generated in may ways.
There are many standards you can use to generate these certificates. These are generated for every user.
- These certificates could contain permissions regarding the data that actors can access.
- This process of generating certificate for a user is known as enrolment.
- These certificates can also be generated using OpenSSL or any other tool, but Fabric-CA is a high quality tool provided.

## 2. Fabric Certificate Authority:
- Fabric peer is where the ledger and the blockchain is stored.
- The peer can update or query the ledger data. 
- A peer can be part of multiple channels(will be explained later). In simple terms channels can what can be used to achieve isolation in a hyperledger fabric network
- By adding more peers with proper load balancing we can scale the hyperledger blockchain.

## 3. Ordering Service:
- This is the heart of the consensus algorithm for Hyperledger.
- Before anything is committed to the ledger it should pass through the ordering service. Ordering service creates the blocks that are signed. The ordering service sends these blocks to the peers whenever a block is full and the peers verify the blocks cryptographically and add them to the ledger.
- In general ordering service is responsible for deciding which operation is before or after another operation.

# Concept of channels in hyperledger fabric:

- Every channel is independent of each other. Each can be thought of as an independent subset of hyperledger fabric network.
- Inter-channel communication is not possible, hence we can achieve isolation.
- Suppose there are 3 peers A,B and C within channel 1. A and B want to communicate with each other indepented of C. They can open a new channel and communicate and exchange data independent of C.
- Every peer inside hyperledger fabric must be part of a channel. Whenever a peer is created it must join at least one channel. This joining process should be agreed upon the parties that are already members of the channel.

# Concept of chaincode:

- Smart contract is called chaincode in context of hyperledger.
- Peer executes the chaincode to verify transactions.
- The only thing that can manipulate and read the ledger is the chaincode.
- The chaincode must be part of a channel.
- Specific business logic can be written in different chaincodes.

## Next Steps
--------------------

[Accessing your AWS virtual machine using SSH](ssh_instruction.md)


[Installing all pre-requisites required to run hyperledger fabric and hyperledger composer](prereqs.md)

[Bringing up your first hyperledger fabric network](walkthrough.md)

[The final submission requirement guidelines regarding building a custom hyperledger fabric network](custom_network.md)

