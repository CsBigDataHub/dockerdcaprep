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
```
### Dockerfile Instructions

**Insert nd Image here**
**Insert nd Image here**
**Insert nd Image here**
**Insert nd Image here**
