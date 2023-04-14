# Docker

## Required

- Docker desktop [Download link](https://docs.docker.com/get-docker/)

### or

- Docker ubuntu

Uninstall older versions
` sudo apt-get remove docker docker-engine docker.io containerd runc`

Install last version
`sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin`

---

## Steps

**If using docker desktop be sure you have it _up_ and _running_**

### Pull image of mysql

1. First step is to look for the image in the [Docker Hub](https://hub.docker.com/)

![docker mysql image](https://github.com/brandonruizmora/dockercompose-node-mongo/images/1.png)

2. Here we will be using the latest mysql image available we pull the image using the command _`docker image pull`_

![docker mysql image](https://github.com/brandonruizmora/dockercompose-node-mongo/images/2.png)

3. After the download is completed we verify the image using the command _`docker images`_

![docker mysql image](https://github.com/brandonruizmora/dockercompose-node-mongo/images/3.png)