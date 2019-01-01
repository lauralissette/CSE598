Build Your First Network Walkthrough
-------------------------

Firstly we need to ensure that the current user can run docker commands using sudo

We can enable this using the following command:
```
sudo usermod -a -G docker $USER
```
Now we need to reboot the virtual machine in order to save these changes:
```
sudo reboot
```
Wait for about 1 minute and then 
SSH into the virtual machine once more using the command:
```
ssh -i .ssh/labsuser.pem ubuntu@<PublicIP>                                    
```
Now we can download and install Samples, Binaries and Docker Images related to hyperledger fabric. We will be using hyperledger fabric version 1.1.0 for this project.

The following command will download and install all the binaries and docker images required:

```
sudo curl -sSL http://bit.ly/2ysbOFE | bash -s 1.1.0
```
If you want to use a specific version of hyperledger in the future kust replace 1.1.0 with the version that you want to use:

```
sudo curl -sSL http://bit.ly/2ysbOFE | bash -s <version>
```
In this walkthrough we'll be running the default scripts provided in the fabric samples to bring up a network consisting of 4 peers representing 2 different organizations and an orderer node.

In the next stage you'll be making your own docker file with a different network configuration.

What you'll be using:

Inside the **fabric-samples** folder, enter into the **first-network** folder.

A scipt named byfn.sh exists in this folder. This can be run by providing the following options:

```
Usage:
  byfn.sh <mode> [-c <channel name>] [-t <timeout>] [-d <delay>] [-f <docker-compose-file>] [-s <dbtype>] [-l <language>] [-i <imagetag>] [-v]
    <mode> - one of 'up', 'down', 'restart', 'generate' or 'upgrade'
      - 'up' - bring up the network with docker-compose up
      - 'down' - clear the network with docker-compose down
      - 'restart' - restart the network
      - 'generate' - generate required certificates and genesis block
      - 'upgrade'  - upgrade the network from v1.0.x to v1.1
    -c <channel name> - channel name to use (defaults to "mychannel")
    -t <timeout> - CLI timeout duration in seconds (defaults to 10)
    -d <delay> - delay duration in seconds (defaults to 3)
    -f <docker-compose-file> - specify which docker-compose file use (defaults to docker-compose-cli.yaml)
    -s <dbtype> - the database backend to use: goleveldb (default) or couchdb
    -l <language> - the chaincode language: golang (default), node or java
    -i <imagetag> - the tag to be used to launch the network (defaults to "latest")
    -v - verbose mode
  byfn.sh -h (print this message)

Typically, one would first generate the required certificates and
genesis block, then bring up the network. e.g.:

        byfn.sh generate -c mychannel
        byfn.sh up -c mychannel -s couchdb
        byfn.sh up -c mychannel -s couchdb -i 1.1.0-alpha
        byfn.sh up -l node
        byfn.sh down -c mychannel
        byfn.sh upgrade -c mychannel

Taking all defaults:
        byfn.sh generate
        byfn.sh up
        byfn.sh down

```
No need to panic! We'll go through this step by step:

Firstly we need to generate network artifacts.

This first step generates all of the certificates and keys for our various network entities, the genesis block used to bootstrap the ordering service, and a collection of configuration transactions required to configure a Channel.

We can use the following command to do that:

```
./byfn.sh generate
```
Next you can bring up the network with this command:

```
./byfn.sh up
```
The above command will compile Golang chaincode images and spin up the corresponding containers. Go is the default chaincode language, however there is also support for Node.js and Java chaincode.

* One by one each of the peers will be launched and they will join 'mychannel'. 
* Also anchor peers will be set for each organozation so that there can be inter-organization communication. 
* Sample queries will be run on each peer
* To view all the containers running this command can be used:

```
docker ps
```
In order to bring down this network this command can be used:
```
./byfn.sh down
```
Running docker ps again, we notice that all the containers have been destroyed.

Now we will tweak this to generate our own network configuration.