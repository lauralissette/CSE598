Install pre-requisites:
-----------------------
The allocated virtual machine has Ubuntu 16.04 LTS installed on it. 
To get started with building a hyperledger fabric network, we need to first install docker
Install docker using the following commands:

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

Once we have docker installed, please go to the below link and install all pre-requisites from the github
repository and run the dash client:

```
https://github.com/dashpay/dash/
```
