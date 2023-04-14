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

## First example

Create MySQL container and use with MySQL Workbench

### Steps

**If using docker desktop be sure you have it _up_ and _running_**

#### Pull image of mysql

1. First step is to look for the image in the [Docker Hub](https://hub.docker.com/)

![docker hub mysql image](https://github.com/brandonruizmora/docker-mysql/blob/master/images/1.png?raw=true)

2. Here we will be using the latest mysql image available we pull the image using the command _`docker image pull`_

![docker mysql image pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/2.png?raw=true)

3. After the download is completed we verify the image using the command _`docker images`_

![docker mysql image verification](https://github.com/brandonruizmora/docker-mysql/blob/master/images/3.png?raw=true)

#### Create and Run the container of mysql

1. To create and run the container of mysql we can use the command _`docker container run`_ here we provide _the container name, environment variables, define localhost port, to run in background mode and the image of mysql_

![docker mysql create container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/4.png?raw=true)

2. This will provide a container id and we can verify the container using the command _`docker ps`_ . We see that container id correspond to the container small id and the port 3306 of our host is mapped to the port 3306 of the container

![docker mysql create container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/5.png?raw=true)

3. Finally we can use MySQL Workbench to verify our container is up and running. We provide the hostname: **localhost** port: **3306** username: **root** and password: **root** .

![docker mysql create container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/6.png?raw=true)

![docker mysql create container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/7.png?raw=true)

4.- At end we can stop the container execution using the command _`docker container stop`_ , remove container using the command _`docker container rm`_ , and remove image of mysql using the command _`docker image rm`_ .


![docker mysql remove container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/8.png?raw=true)


--- 

## Second example

Create MySQL container and use with Adminer container

### Steps

**If using docker desktop be sure you have it _up_ and _running_**

#### Pull image of mysql

1. First step is to look for the image in the [Docker Hub](https://hub.docker.com/)

![docker hub mysql image](https://github.com/brandonruizmora/docker-mysql/blob/master/images/1.png?raw=true)

2. Here we will be using the latest mysql image available we pull the image using the command _`docker image pull`_

![docker mysql image pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/2.png?raw=true)

3. After the download is completed we verify the image using the command _`docker images`_

![docker mysql image verification](https://github.com/brandonruizmora/docker-mysql/blob/master/images/3.png?raw=true)

#### Pull image of adminer

1. First step is to look for the image in the [Docker Hub](https://hub.docker.com/)

![docker hub adminer image](https://github.com/brandonruizmora/docker-mysql/blob/master/images/9.png?raw=true)

2. Here we will be using the latest adminer image available we pull the image using the command _`docker image pull`_

![docker adminer image pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/10.png?raw=true)

3. After the download is completed we verify the image using the command _`docker images`_

![docker adminer image verification](https://github.com/brandonruizmora/docker-mysql/blob/master/images/11.png?raw=true)

#### Create and Run the container of mysql

1. To create and run the container of mysql we can use the command _`docker container run`_ here we provide _the container name, environment variables, define localhost port, to run in background mode and the image of mysql_

2. This will provide a container id and we can verify the container using the command _`docker ps`_ . We see that container id correspond to the container small id and the port 3306 of our host is mapped to the port 3306 of the container

![docker mysql create container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/12.png?raw=true)

#### Create and Run the container of adminer


