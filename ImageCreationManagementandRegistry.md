# Image Creation Management and Registry

## Understanding Docker Images

* an Image is an executable package that includes everything needed to run an application, including the code, a runtime, libraries, environmental variables and configuration files.

### Understanding Layes with Docker Images

**Insert 1st Image here**

* The Docker image union file system, as it's called, starts off at the bottom-most layer, with what they call a **manifest**. A manifest is, as you would expect, just like a container manifest on a container ship. This manifest is a document. In this case, it's a little bit of code, that describes what's inside the container. So, we start off with this description of the container. And then on top of that, you have the first container layer.

**Insert 2nd Image here**

### Dockerfile

* A Dockerfile is a text file that contains all the commands in order, needed to build a given image. The Dockerfile is executed using the docker build command.

* [Dockerfile-reference](https://docs.docker.com/engine/reference/builder/) 

```shell
man dockerfile
docker image inspect <Image-id>
docker image history <Image-id>
```

### Dockerfile Instructions

**Insert 3nd Image here**
**Insert 4nd Image here**
**Insert 5nd Image here**
**Insert 6nd Image here**

### Managing images with the CLI

* **Dangling Images** - Dangling image is an image that was built, but doesn't have a tag

```shell
docker image <command>
docker image prune ## removes unused/Dangling images
docker image prune -a ## prunes all images that are unused by containers
```

## Managing Docker images

### Inspecting images

* [Docker-Image-inspect](https://docs.docker.com/engine/reference/commandline/image_inspect/)

```shell
docker inspect
docker image inspect <image> --format='{{.id}}' ##this will give id of image
docker image inspect <image> --format='{{json .ContainerConfig}}' ## will give container configuration in json format
docker image inspect <image> --format='{{.ContainerConfig.Hostname}} ## will give you the host name
```

### Using image tagging

* [DockerTagsDocumentation](https://docs.docker.com/engine/reference/commandline/tag/)


