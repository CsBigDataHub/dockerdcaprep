# Docker Essential Training: 1 Installation and Configuration
## Sizing Docker
* Before you install Docker, it's important to understand the prerequisites and insure that your hardware is sized appropriately. For the community edition there are no specific hardware requirements other than those of whatever operating system you're installing Docker on. For Docker Enterprise edition, because Universal Control Plane and Docker Trusted Registry, which are important pieces of the enterprise edition, require much more resources than Docker's engine itself, you should be aware of the specific guidelines for deploying UCP and DTR.
*[Docker best practices](https://success.docker.com/article/docker-ee-best-practices)

## Universal Control Plane
* With the highest level of Docker Enterprise the Universal Control Plane can also include secure image scanning and continuous monitoring of your images in the registry. Finally, Docker Enterprise Edition includes Docker Trusted Registry or DTR.
* With UCP you can run thousands of nodes with tens of thousands of containers managed as services and stacks across your Docker infrastructure. The Docker Universal Control Plane allows you to manage all of that plus the associated networks and storage from a single graphical interface.
## Docker NameSpaces
*The Docker engine utilizes something called 'Namespaces' to isolate what's happening in the running containers from the operating system that those containers are running on. With Namespaces the kernal resources such as the process ID, user IDs, network storage, and inner process communications or IPC, can all be virtualized and shared between the host operating system and the containers running on top. Namespaces weren't created by Docker.
## Docker control groups and Limit a container's resources
* [Limit a container's resources](https://docs.docker.com/config/containers/resource_constraints/)
* To add user to a group use -- sudo usermod -aG docker $USER
