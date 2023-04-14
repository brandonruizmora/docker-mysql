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

#### **Pull image of mysql**

1. First step is to look for the image in the [Docker Hub](https://hub.docker.com/)

![docker hub mysql image](https://github.com/brandonruizmora/docker-mysql/blob/master/images/1.png?raw=true)

2. Here we will be using the latest mysql image available we pull the image using the command _`docker image pull`_

![docker mysql image pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/2.png?raw=true)

3. After the download is completed we verify the image using the command _`docker images`_

![docker mysql image verification](https://github.com/brandonruizmora/docker-mysql/blob/master/images/3.png?raw=true)

#### **Create and Run the container of mysql**

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

#### **Pull image of mysql**

1. First step is to look for the image in the [Docker Hub](https://hub.docker.com/)

![docker hub mysql image](https://github.com/brandonruizmora/docker-mysql/blob/master/images/1.png?raw=true)

2. Here we will be using the latest mysql image available we pull the image using the command _`docker image pull`_

![docker mysql image pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/2.png?raw=true)

3. After the download is completed we verify the image using the command _`docker images`_

![docker mysql image verification](https://github.com/brandonruizmora/docker-mysql/blob/master/images/3.png?raw=true)

#### **Pull image of adminer**

1. First step is to look for the image in the [Docker Hub](https://hub.docker.com/)

![docker hub adminer image](https://github.com/brandonruizmora/docker-mysql/blob/master/images/9.png?raw=true)

2. Here we will be using the latest adminer image available we pull the image using the command _`docker image pull`_

![docker adminer image pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/10.png?raw=true)

3. After the download is completed we verify the image using the command _`docker images`_

![docker adminer image verification](https://github.com/brandonruizmora/docker-mysql/blob/master/images/11.png?raw=true)

#### **Create and Run the container of mysql**

1. To create and run the container of mysql we can use the command _`docker run`_ here we provide _the container name, environment variables, define localhost port, to run in background mode and the image of mysql_

2. This will provide a container id and we can verify the container using the command _`docker ps`_ . We see that container id correspond to the container small id and the port 3306 of our host is mapped to the port 3306 of the container

![docker mysql create container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/12.png?raw=true)

#### **Create and Run the container of adminer**

1. To create and run the container of adminer we can use the command _`docker run`_ here we provide _the container name, link to another container, define localhost port, to run in background mode and the image of adminer_

2. This will provide a container id and we can verify the container using the command _`docker ps`_ . We see that container id correspond to the container small id and the port 3306 of our host is mapped to the port 3306 of the container

![docker mysql create container](https://github.com/brandonruizmora/docker-mysql/blob/master/images/13.png?raw=true)

#### **Check connection of adminer and mysql**

We link the container of adminer to the container of mysql using the option --link. Now we can access to **localhost:8080** and set params System: _MySQL_, Server: _mysqlito_, Username: _userdb_, password: _passworddb_, Database: _mysqldb_.Those where defined in mysql container creation.

![adminer connection](https://github.com/brandonruizmora/docker-mysql/blob/master/images/14.png?raw=true)


![adminer connection](https://github.com/brandonruizmora/docker-mysql/blob/master/images/15.png?raw=true)

#### **Stop containers, remove it and remove images**

1. Finally we can stop containers with command _`docker stop`_

2. Remove containers with command _`docker rm`_

3. Verify containers are removed with command _`docker ps -a`_

4. Remove images with command _`docker image rm`_

5. Verify images are removed with command _`docker images`_

![remove containers and images](https://github.com/brandonruizmora/docker-mysql/blob/master/images/16.png?raw=true)

--- 

## Third example

Now we are going to use docker-compose

This will help us to download images, create, (re)build, starts multi-containers all of that with a single file and command

### Steps

**If using docker desktop be sure you have it _up_ and _running_**

#### **Create docker-compose.yml (define multi-container application)**

**docker-compose.yml** file allows you to configure and document all your application's service dependencies (other services, cache, databases, queues, etc.). Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).

What is defined in the file are this:
- **version** Specifies the version of the Docker Compose syntax to be used in the file.
- **services** Defines the individual services (containers) that make up the application. _Each service is specified as a key-value pair, where the key is the name of the service and the value is a set of properties that configure the service. Properties can include the Docker image to be used, environment variables, ports to be exposed, volumes to be mounted, and other configurations._
- **networks** Defines the networks to be used by the services. _Networks enable communication between different services within the same Docker Compose application._
- **volumes** Defines the volumes to be used by the services. _Volumes are used to persist data across container restarts or to share data between containers._
- **configs and secrets** Define configurations and secrets to be used by the services. _Configurations and secrets are used to externalize configuration data and sensitive information, respectively, from the docker-compose.yml file._
- **deploy** Specifies configurations related to deployment of the services _in a swarm mode Docker cluster, such as replicas, placement constraints, and update policies._

1. To pull required images we use command _`docker-compose pull`_ this will pull images defined in _docker-compose.yml_

![docker-compose pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/17.png?raw=true)

2. We verify the images downloaded _`docker image ls`_

![docker-compose pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/18.png?raw=true)

3. Now to run the containers defined in docker-compose we use the command _`docker-compose up -d`_ this will create and start the containers.

![docker-compose pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/19.png?raw=true)

4. We can verify in **localhost:8080** and set params System: _MySQL_, Server: _mysqlito_, Username: _userdb_, password: _passworddb_, Database: _mysqldb_.Those where defined in mysql container creation.

![docker-compose pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/14.png?raw=true)

![docker-compose pull](https://github.com/brandonruizmora/docker-mysql/blob/master/images/15.png?raw=true)

#### **Stop containers, remove it and remove images**

1. Finally we can stop containers with command _`docker stop`_

2. Remove containers with command _`docker rm`_

3. Verify containers are removed with command _`docker ps -a`_

4. Remove images with command _`docker image rm`_

5. Verify images are removed with command _`docker images`_

![remove containers and images](https://github.com/brandonruizmora/docker-mysql/blob/master/images/16.png?raw=true)
