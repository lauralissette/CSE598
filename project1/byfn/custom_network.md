Creating a custom hyperledger fabric network configuration
----------------------------------------------------------
We will build a network configuration from scratch including all the identity certificates, organizations, peer configurations, channel configurations.

An overview of the network we want to build:

* 3 Organizations
* Every organization has their own channel
* Every channel consists of 5 peers
* Within each channel one of the peers acts as an anchor peer allowing inter-channel configuration.
* There are 3 orderers for the network