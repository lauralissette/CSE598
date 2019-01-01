Install pre-requisites:
-----------------------
The allocated virtual machine has Ubuntu 16.04 LTS installed on it. 
To get started with building a hyperledger fabric network, we need to first install docker
Install docker and docker compose using the following commands:

Remove the older versions of docker installed:
```
sudo apt-get remove docker docker-engine docker.io

```
Update the apt package index:

```
sudo apt-get update
```
Install packages to allow apt to use a repository over HTTPS:
```
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```
Add Docker’s official GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Add the stable repository:
```
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   (lsb_release -cs) \
   Stable"
```
```
sudo apt-get update
```
Install Docker CE

```
sudo apt-get install docker-ce
```
Check that the docker version is above 17.06.2

```
docker --version
```
To install docker compose use the following command:

```
sudo curl -L https://github.com/docker/compose/releases/download/1.18.0/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
```
Change permissions to the docker-compose folder:

```
sudo chmod +x /usr/local/bin/docker-compose
```
Check that the docker-compose version is above 1.14.0 using the following command:

```
docker-compose --version
```
If there are issues with permissions of docker-composer, use the following command to resolve that:

```
sudo usermod -a -G docker $USER
```
Next we need to install Go language (version higher than v1.10):
```
wget https://dl.google.com/go/go1.11.2.linux-amd64.tar.gz
tar -xvf go1.11.2.linux-amd64.tar.gz
sudo mv go /usr/local
```
Now we will add required paths for Go installation to the bash profile:

```
sudo nano ~/.profile
```
Add the following lines at the end of the file:

```
export GOPATH=$HOME/work
export PATH=$PATH:/usr/local/go/bin:$GOPATH/bin
```
Press Ctrl+X > y > Enter 

Then type in the following command so that changes made to profile are applied:

```
source ~/.profile
```
To test your installation type the following command:
```
go version
```
It should give out the following output:
```
> go version go1.11.2 linux/amd64
```

For the installing the remaining pre-requisites the following command can be used:

```
curl -O https://hyperledger.github.io/composer/latest/prereqs-ubuntu.sh

sudo chmod u+x prereqs-ubuntu.sh

./prereqs-ubuntu.sh
```
After this point we're done installing pre-requisistes and get started with using code from the hyperledger fabric repository
