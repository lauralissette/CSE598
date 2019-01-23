Build Your Own Network Walkthrough
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
Now we can start writing scripts to write our own blockcain network.

You are required to do the below:

Use the github repository 

```
https://github.com/dashpay/dash/
```
to 

- install all the pre-requisites in order to run the dash client
- run a copy of dash client, play with the RPC calls and see how it works.
( Please run it in regtest mode. testnet or the mainnet option downloads the whole blockshain before you can do anything, it requires more storage than provided in the AWS machine.)

- the submission should be in a folder called project\_network

- the submission should have 2 mandatory items. a Dockerfile and the dash source code that you will use to create your network. 

- the dash binaries should be statically created otherwise they will not run in a container because of the dependencies.

