# Project 2 Phase I Overview and Requirements


## Phase I: Experimenting with public blockchains using dashpay
----------------------------------------------------------------

**Overview:**

- In Phase I of this project, you will learn about various pre-requisites to install and use a cryptocurrency, and you will be tested on the correctness of the nature of the blockchain network. 

- All work will be done on an AWS virtual machine where you will bring up your own blockchain decentralized network by writing your own scripts.


**Technologies used:**

- Bitcoin/dash
- Docker
- Git

**Deliverables:**

- A folder that contains a single shell file that runs a decentralized blockchain network (NOTE: You will need to submit a folder with all files, but everything should be automated using a single shell file named submit.sh.)

- The folder name should be public\_network, which should contain submit.sh, a Dockerfile, and the dash source code that you are using to build the containers. You may clone the dash source too in your submit.sh.

--------------------------------------

**Custom Network Requirements:**

This phase requires you to run a custom public blockchain network that meets the following requirements listed below. Further details of the network are given in the named network.md.

* 24 full nodes 
* Every node is a docker container and responds to all RPC commands on dash client
* Every node is connected to minimum 3 nodes and maximum 6 nodes in the network
* All nodes should be able to create transactions in regtest mode and mine blocks.
* The tags of all docker containers should be node_$number. The nodes, therefore should be named node_0 to node_23. In order to test this, you should be able to run docker exec -t node_0 dash-cli dash_rpc_command.

-------------------------------------
**Next Steps:**

- Your next step is to open the file named ssh_instructions.md and complete the steps it outlines for accessing the AWS Virtual Machine.
- Then you will need to install all necessary pre-requisites required for dash wallet to run. (These usally are the same for all cryptocurrencies forked from bitcoin). To complete this task, use the file named prereqs.md.
- After you install all necessary pre-requisites, proceed to the file named network.md.
