# Storage and Volumes

## Understanding Docker Storage

* **Volumes**

        - Docker Volumes are the recommended way to persist data, or to store persistent data that needs to live beyond the life of a container. 

        - Docker Volume data is stored in var/lib/docker/volumes if you're running Docker on Linux. 

* **Bind Mounts**

        - Another option for data storage when using Docker containers is to use a bind mount.

        - A bind mount has limited functionality, and you have to use the exact file path on the host. 

        - For that reason, and a number of other reasons, Docker Volumes are highly recommended over Docker bind mounts.

* **Tmpfs Mount**

        -  A third option that you have is called a tempfs mount. 

        -  Tempfs mounts are stored only in the host memory in Linux, and this is the least recommended option for data storage when using Docker containers. 

    **1st pic here**

        -  That container is running on top of a file system, and Docker has access to a specific area in that file system. 
        -  A bind mount directly accesses the file system, whereas a Docker Volume stores its data inside the designated Docker area within the file system.
        -  On the other hand, a tempfs mount stores its data inside the memory on the host where the container is running.
        -  It's important to keep these three different options in mind when you consider data storage for Docker containers, with the Docker Volume always being the most highly-recommended option. 

### Compare object storage solutions

    **2nd pic here**

### Analyze Docker's layered storage

```shell
docker image inspect <docker-id>
docker history <docker-id>
```

## Configure Docker Storage

[select-storage-driver](https://docs.docker.com/storage/storagedriver/select-storage-driver/)
[overlayfs-storage-driver](https://docs.docker.com/storage/storagedriver/overlayfs-driver)
[Docker-RHEL-Stroge-Issue](https://batmat.net/2015/08/26/docker-storage-driver-dont-use-devicemapper/)

### Change storage driver

```shell
docker info ## to find the storage driver
sudo systemctl stop docker
sudo cp -au /var/lib/docker $HOME ##backing up
docker save ## to save and back-up images

```

### Device mapper

[device-mapper-driver](https://docs.docker.com/storage/storagedriver/device-mapper-driver/)

### Docker volumes

[Volumes](https://docs.docker.com/storage/volumes/)