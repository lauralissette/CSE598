# Introduction to Project 1 

## Experimenting with permissioned blockchains using Hyperledger
----------------------------------------------------------------

This project consists of two phases. Each phase is described below, including submission requirements and due dates.

## Phase 1: Build Your First Network (use byfn folder)
--------------------------------------

- In this phase you will learn about various tools required to install and use hyperledger fabric.
- Hyperledger Fabric is an enterprise grade distributed ledger based on blockchain technology that uses smart contracts to enforce trust between parties.
- The first task in this project is to install all necessary tools related to hyperledger fabric and hyperledger composer on an AWS virtual machine and bring up your first hyperledger network using the scripts provided.
- Then you will experiment with .yaml files to create a specified hyperledger fabric network configuration and explore ways in which the cryptographic material for the network can be generated.

**Technologies used:**

- [Hyperledger Fabric](https://hyperledger-fabric.readthedocs.io/en/release-1.3/)
- [Docker](https://docs.docker.com/)
- [Git](https://git-scm.com/docs)
- [Cryptogen tool](https://hyperledger-fabric.readthedocs.io/en/release-1.3/commands/cryptogen.html)


**Deliverables:**

- docker-compose.yaml file used to configure the specified hyperledger fabric network
- crypto-config.yaml file used to generate the cryptographic material for the hyperledger fabric network

**Submission Guidelines:**

You need to submit the entire custom_network folder by uploading it to your work directory on Vocareum. **AWS virtual machine contents will not be submitted for grading**. You should use **scp** to copy your work onto the Vocareum machine inside the work directory and then submit it. 

**Due Date:**

- Your final Phase 1 folder submisison through Vocareum is due by 11:59 p.m. Wednesday, January 25, 2019.


**Using the byfn Files:**
 
 Use the files in the byfn (Build Your First Network) folder in the following order:
 
 (1) **ssh_instructions.md.**  This file contains instructions for accessing the AWS Virtual Machine.
 
 (2) **prereqs.md.**  This file provides instructions for installing the prerequisites you need and the environment for HyperLedger Composer.
 
 (3) **walkthrough.md.**  This file walks you through the process of building your first network.
 
 (4) **custom_network.md.**  This file presents how to create a custom HyperLedger Fabric network configuration as well as how to complete Phase I.
 
 

## Phase 2: Supply Chain Network Application (use supply-chain folder)
--------------------------------------

- In this phase you will learn about various tools required to build a business application using hyperledger composer.
- Hyperledger Composer is a set of collaboration tools, built with JavaScript, for building blockchain business networks that make it simple and fast for business owners and developers to create smart contracts and blockchain applications to solve business problems.
- You will build an application that tracks the transaction history and attribute changes associated with the life-cycle of an order propagating through a supply chain.
- You will learn about building a model for a business application and also write transaction processor functions, permissions for various actors, and transaction inside the supply chain network.

**Technologies Used:**

- [Hyperledger Fabric](https://hyperledger-fabric.readthedocs.io/en/release-1.3/)
- [Hyperledger Composer](https://hyperledger.github.io/composer/latest/introduction/introduction.html)
- [NodeJS](https://nodejs.org/en/docs/)
- [Testing Frameworks: Mocha and Chai]()
- [Git](https://git-scm.com/docs) 


**Deliverables:**

- Entire folder named **supply-chain**

**Submission Guidelines:**

You need to submit the entire supply-chain folder by uploading it to your work directory on Vocareum. **AWS virtual machine contents will not be submitted for grading**. You should use **scp** to copy your work onto the Vocareum machine inside the work directory and then submit it.

**Make sure your network version inside package.json is set to 0.0.1 before submitting.**

**Due Date:**

Your final Phase 2 package submisison through Vocareum is due by 11:59 p.m. Sunday, February 3, 2019.

# Report

A comprehensive project report describing your work for Project 1 is also due for this project. You will find the report template and the staff-graded project tool for submitting your report at the end of Week 4 in the course on Coursera. Your report should strictly follow the report specifications provided.

**Due Date:**

Your Project 1 report submitted through Coursera is due by 11:59 p.m. Sunday, February 3, 2019.

**Using the supply-chain Files:**

Use the sub-folders and files in the supply-chain folder in the following order (and note those you may ignore):

(1) **models (folder).**  This folder contains the model for a supply chain network.

(2) **lib (folder).**  This folder contains logic for smart contracts.

(3) **permissions.acl.** This file contains permissions for various actors within the network.

**Test (folder).**  This folder contains a test file that you may ignore, but it needs to be present.

**.eslintrc.yml.**  You may ignore this system configuration file, but it needs to be present.

**package.json.**  You may ignore this system configuration file, but it needs to be present.






