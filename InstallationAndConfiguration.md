# Docker Essential Training: 1 Installation and Configuration

## Sizing Docker
* Before you install Docker, it's important to understand the prerequisites and insure that your hardware is sized appropriately. For the community edition there are no specific hardware requirements other than those of whatever operating system you're installing Docker on. For Docker Enterprise edition, because Universal Control Plane and Docker Trusted Registry, which are important pieces of the enterprise edition, require much more resources than Docker's engine itself, you should be aware of the specific guidelines for deploying UCP and DTR.
* [Docker best practices](https://success.docker.com/article/docker-ee-best-practices)

## Universal Control Plane
* With the highest level of Docker Enterprise the Universal Control Plane can also include secure image scanning and continuous monitoring of your images in the registry. Finally, Docker Enterprise Edition includes Docker Trusted Registry or DTR.
* [Install UCP for production](https://docs.docker.com/datacenter/ucp/2.2/guides/admin/install)

## Docker NameSpaces
* The Docker engine utilizes something called 'NamespacesInstall UCP for production' to isolate what's happening in the running containers from the operating system that those containers are running on. With Namespaces the kernal resources such as the process ID, user IDs, network storage, and inner process communications or IPC, can all be virtualized and shared between the host operating system and the containers running on top. Namespaces weren't created by Docker.

![Namespaces](1-Installation-and-configuration)
## Docker control groups and Limit a container's resources
* [Limit a container's resources](https://docs.docker.com/config/containers/resource_constraints/)
* To add user to a group use -- sudo usermod -aG docker $USER

## Docker storage drivers
* [Docker storage drivers](https://docs.docker.com/storage/storagedriver/select-storage-driver/)

## Docker swarm
* Docker Swarm is the cluster management and orchestration feature that's built into the Docker Engine. Docker Swarm is available whether or not you have Docker Community Edition or Enterprise Edition.
* To add a node to docker swarm , one option is to do it from UCP which provides command -- 
```shell
docker swarm join --token <token-id> <ipaddress:port>
```
## Configuring Docker to start on boot
* [Docker to start on boot](https://docs.docker.com/install/linux/linux-postinstall/#configure-docker-to-start-on-boot)


## Backing up Docker
* [Backing Docker EE](https://docs.docker.com/eebackup)
* [Backing Swarm cluster](https://docs.docker.com/engine/swarm/admin_guide/#back-up-the-swarm)
### Backing up swarm
* stop Docker 
* go to /var/lib/docker
* copy the swarm directory to  back location
### Backing up UCP
* https://docs.docker.com/datacenter/ucp/2.2/guides/admin/backups-and-disaster-recovery/
### Backing up Docker Registry
* https://docs.docker.com/datacenter/dtr/2.3/guides/admin/backups-and-disaster-recovery/#backup-image-content

## Installing Docker Trusted Registry
* [Install Docker Trusted Registry](https://docs.docker.com/datacenter/dtr/2.4/guides/admin/install/)

## Docker Logging
* https://docs.docker.com/config/containers/logging/configure/

```shell
 docker info | grep 'Logger Driver'
 cd /etc/docker
 > deamon.json
 docker run --log-driver=syslog --log-opt syslog-address=udp://1.1.1.1 <containers> # to chage log driver while running the container
```

## Analyzing Docker errors
* [Troubleshoot](https://docs.docker.com/install/linux/linux-postinstall/#troubleshooting)

