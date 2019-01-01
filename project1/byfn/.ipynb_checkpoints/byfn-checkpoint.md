{
 "cells": [
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Install pre-requisites:\n",
    "-------------------------------\n"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "The allocated virtual machine has Ubuntu 16.04 LTS installed on it. \n",
    "To get started with building a hyperledger fabric network, we need to first install docker\n",
    "Install docker and docker compose using the following commands:"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": [
    "Remove the older versions of docker installed:\n",
    "```\n",
    "sudo apt-get remove docker docker-engine docker.io\n",
    "\n",
    "```\n",
    "Update the apt package index:\n",
    "\n",
    "```\n",
    "sudo apt-get update\n",
    "```\n",
    "Install packages to allow apt to use a repository over HTTPS:\n",
    "```\n",
    "sudo apt-get install \\\n",
    "    apt-transport-https \\\n",
    "    ca-certificates \\\n",
    "    curl \\\n",
    "    software-properties-common\n",
    "```\n",
    "Add Docker’s official GPG key:\n",
    "```\n",
    "curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -\n",
    "```\n",
    "Add the stable repository:\n",
    "```\n",
    "sudo add-apt-repository \\\n",
    "   \"deb [arch=amd64] https://download.docker.com/linux/ubuntu \\\n",
    "   (lsb_release -cs) \\\n",
    "   Stable\"\n",
    "```"
   ]
  },
  {
   "cell_type": "markdown",
   "metadata": {},
   "source": []
  },
  {
   "cell_type": "code",
   "execution_count": null,
   "metadata": {},
   "outputs": [],
   "source": []
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 2",
   "language": "python",
   "name": "python2"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 2
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython2",
   "version": "2.7.12"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 2
}
