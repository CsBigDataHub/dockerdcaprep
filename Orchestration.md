# Docker Essential Training: 2 Orchestration

## Getting started with Docker Swarm
### Intro to Docker Swarm
* Docker Swarm is available whether or not you have Docker Community Edition or Enterprise Edition. The Docker Swarm functionality comes from a separate project that Docker calls Swarmkit. A swarm cluster of Docker hosts or nodes, as they're called, is a highly available cluster of servers that runs in swarm mode. What's so powerful about Docker Swarm is that you can create what they call a service.
* For example, we could have a web server service with tens or even hundreds of web servers and define its desired state. For example, you could say that you want port 80 exposed for all the web servers, you could define the storage that all the web servers need and you could say that you always want to have, for example, 100 web servers running. Docker Swarm can take that service definition and act on it to ensure that it's always available.

### Set up a Docker Swarm
* [Setup-Docker-swarm](https://docs.docker.com/engine/swarm/)
* [Setup-Tutorial](https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/)
```shell
docker swarm init ## to initialze the swarm
docker swarm join-token worker ## to add worker to swarm
```

### Nodes, services, containers, and tasks
* [deploy-service](https://docs.docker.com/engine/swarm/swarm-tutorial/create-swarm/deply-service)
```shell
docker service create --replicas <no. of replicas> --name <service-name> <docker-image-name>
```
* Difference btw container and services
- **Insert picture here**

### Locking a Swarm Cluster
[lock-swarm-manager](https://docs.docker.com/engine/swarm/swarm_manager_locking/)
* Securing swarm is also important because of the ability for Docker to store and distribute secret keys for other applications with the Docker secrets feature. Any time that the Docker daemon restarts, the keys used to encrypt communication between nodes and the keys used to encrypt the logs on the disc are loaded. With Docker 1.13 and higher, you have the option to better protect the encryption keys used to access the swarm log by having the swarm managers require you to provide this key when they're restarted for security reasons.
```shell
docker swarm init --autolock ## when initialze
docker swarm update --autolock=true ## to enable autolock on existing cluster and it generate a key
docker swarm unlock-key ## to get the key . this only workes when the cluster is up and running . 
docker swarm unlock-key --rotate ## to get new key . 
```
* To unlock a swarm manager after it restarts, you have to run the the docker swarm unlock command and you must provide the key generate by `autolock`. Which of course will be different on different docker swarm clusters. It tells us to make sure that we remember this key or store it in a password manager which is more likely considering the length of the key since you won't be able to restart your Docker swarm managers without it.
* [docker_admin_guide](https://docs.docker.com/engine/swarm/admin_guide/)
* For those swarm cluster managers to be able to make those types of decisions, and ensure that the cluster's state is always healthy, they have to have something called quorum.
- **insert 5 fault tolerance here**
* [swarm-mode-raft-consensus](https://docs.docker.com/engine/swarm/raft/)

- **insert 5 fault tolerance here **

## 

