Creating a custom hyperledger fabric network configuration
----------------------------------------------------------
We will build a network configuration from scratch including all the identity certificates, organizations, peer configurations, channel configurations.

An overview of the network we want to build:

* Domain used: example.com
* 3 Organizations:

Orderer organizations are named

1. Orderer1

Peer Organizations are named:

1. Org1
2. Org2
3. Org3


* Every organization has their own channel
* Every organization consists of 5 peers
* Within each organization one of the peers acts as an anchor peer allowing inter-channel communication.
* There is a single orderer for the network.

Guidelines for completing the project:
------------------------

- We will first start with cryptographic configuration (crypto-config) which will be a yaml based configuration.

- Make a new folder and call it custom_network.

- Copy the binaries from the **fabric-samples/bin** folder to this **custom_network folder** using the following command:

```
cp <path to fabric-samples>/bin/* <path to custom_network>
```
- These binaries will be used to generate network artifacts.
-We're also going to refer to **crypto-config.yaml** file from **first-network** folder to build our custom network.

- Copy that file into **custom_network** folder using the following command:

```
cp <path to fabric-samples>/first-network/crypto-config.yaml* <path to custom_network>

```

Now there are couple of things we need to understand in this yaml file:

- We have to make sections for 2 kinds of organizations, orderers and peers.'

- For the sake of submission we're using a single orderer also known as solo ordering

- However it is **NEVER** absolutely **NEVER**  advised to use solo ordering in production mode, since it is not crash fault tolerant.(Apache Kafka based ordering is used)

- To understand more about yaml files, it is recommended that you read all the comments properly.
ted.

- Using this **crypto-config.yaml** all the certificated will be generated. These certificates basically decide *"Who is Who"* within the hyperledger fabric network.

- Hyperledger is organized in **organizations**. These organizations consists of peers.

- Even if peers exist on different physical machines they might be present in the same organization.

- Peers can work with each other only if they are in the same organization. Inter organization peer communication is not possible (with the exception of anchor peers).

- Certificates define the identity of every single entity inside the network.

- Next thing we need to define is the domain. This domain will be used by other member to locate the resource. It can be a private level domain like example.com that can be resolved locally.

- Every organization will have a different domain name.

- Let the ordered domain be example.com.

- Peer domain names will vary as per organizations. For eg. Org1 should have domain names org1.example.com and so on.

- We will follow the convention to have domain names in lower case.

- The template parameter at the very bottom of the file controls the number of peers within every organization.

- The first count parameter governs the number of peers.

- The second count parameter governs the number of users that each peer connects to.(Keep this as 1 for the sake of this project).

- The domain name for each peer will be peer0.org1.example.com and so on.

Once everything is defined properly, we are now set to generate cryptographic material using the crytogen tool

We can use this command to do that:

```
cryptogen generate --config=./crypto-config.yaml
```

Some key points regarding cryptographic material generation:
-----------------------------------------------------------
- While regenerating the crypto-config, you should delete the folder first, if it exists, cryptogen won't delete the old folder.
- Cryptogen generates admin certificates for each peer organization which is crucial when executing operations requiring high levels of privilege.

Generating the genesis block:
--------------------------------

- Genesis block is the first block of the blockchain. In hyperledger fabric, however the genesis block has some additional purposes. It stores public keys of all the entities of the network. Also the configuration of the network is inside it.

- Hence the configuration of the hyperledger fabric network is inside the genesis block which is a part of the blockchain itself, rather than storing it on a text file somewhere.

- You should now build this file that will generate the genesis block. We will copy the file **configtx.yaml** file to the **custom_network** folder using the following command:

```
cp <path to fabric-samples>/first-network/configtx.yaml <path to custom_network  folder>
```

On opening this file, we will notice, it consists of many sections. For completion of the first phase of the project this file needs to be configured according to the specification.


After completing this file you can add a create a directory called channel-artifacts in your custom_network folder

```
mkdir channel-artifacts
```

You need to generate profiles according to the specification provided.

- Profiles need to incorporate all conditions which are: 3 organizations, 3 channel configurations and anchor peer configurations.

- Make a profile named ThreeOrgsOrdererGenesis and add 3 organizations to the consortium
- You need to make a profile in such a way that each organization has a seperate channel.
You can name the profiles OrgsChannel1, OrgsChannel2 and so on.


Then we can generate the genesis block using the command:

```
./configtxgen -profile <profile name> -outputBlock ./channel-artifacts/genesis.block
```

We can generate channels using the following command:

```
./configtxgen -profile <profile name> -outpuCreateChannelTx ./channel-artifacts/channel1.tx -channelID <Channel Name>
```
- The channels must be stores as channel1.tx, channel2.tx and so on. The  channelIDs also should be Channel1, Channel2 and so on.

- Also configure the anchor peers properly so that every organizations anchor peer can communicate with other organization.

This command can be used for configuring anchor peers:

```
configtxgen -profile TwoOrgsChannel -outputAnchorPeersUpdate ./channel-artifacts/Org1MSPanchors.tx -channelID $CHANNEL_NAME -asOrg Org1MSP
```

- To complete these files refer to the official hyperledger fabric documentation which can be found here:

[Hyperledger Fabric Documentation](https://hyperledger-fabric.readthedocs.io/en/release-1.3/build_network.html)

**To complete this phase you need to submit both complete only the parts mentioned above**
------------------------------------------------------

Next steps that will be taken : docker-compose file for bringing up the network.

- Docker-compose is a tool that orchestrates docker containers.

- We can start containers manually, using ansible or kubernetes also, but for the sake of this project we will use docker-compose.

- You do not need to write the docker compose script, but bear in mind that the network will be run using the correctly written docker compose script and if there are some error in the config files then the grade for that criteria might be affected in further phases.


Grading Criteria:
--------------------
