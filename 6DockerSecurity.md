# Docker Security
## Understanding Docker Security
### Default Docker Engine Security

![./6DockerSecurity/1.png](./6DockerSecurity/1.png)
![./6DockerSecurity/2.png](./6DockerSecurity/2.png)

[https://docs.docker.com/engine/security/security/](https://docs.docker.com/engine/security/security/)

### Securing Docker Swarm

    - Mutually Authenicated Transfer Layer Security (MTLS) 
    
![./6DockerSecurity/3.png](./6DockerSecurity/3.png)
![./6DockerSecurity/4.png](./6DockerSecurity/4.png)
![./6DockerSecurity/5.png](./6DockerSecurity/5.png)
![./6DockerSecurity/6.png](./6DockerSecurity/6.png)

### Secure Docker to Registry Communincation

[https://success.docker.com/article/security-best-practices-17-03#dtrsecurity](https://success.docker.com/article/security-best-practices-17-03#dtrsecurity)

### Understanding Docker Content trust

    - Signing an image
[https://docs.docker.com/engine/security/trust/content_trust/](https://docs.docker.com/engine/security/trust/content_trust/)

![./6DockerSecurity/7.png](./6DockerSecurity/7.png)
![./6DockerSecurity/8.png](./6DockerSecurity/8.png)

```sh
docker tag nginx:latest <DTR-server or address>/ckoneru/test:<tagname>
export DOCKER_CONTENT_TRUST=1
```
## Configuring Docker Security
### Identifying roles in Universal Control Plane(UCP)

![./6DockerSecurity/9 .png](./6DockerSecurity/9 .png)
![./6DockerSecurity/10.png](./6DockerSecurity/10.png)
![./6DockerSecurity/11.png](./6DockerSecurity/11.png)
![./6DockerSecurity/12.png](./6DockerSecurity/12.png)

### Configuring Role-based access Control in UCP
 - [https://docs.docker.com/ee/ucp/authorization/pull-images/](https://docs.docker.com/ee/ucp/authorization/pull-images/)

### Using external certs with UCP and DTR
- [https://docs.docker.com/ee/ucp/admin/configure/use-your-own-tls-certificates/](https://docs.docker.com/ee/ucp/admin/configure/use-your-own-tls-certificates/)

### Creating UCP client bundles

- Go to UCP : Settings/Profile/Client Bundles/

### Using LDAP/AD with UCP
- Go to UCP : Admin setting/ Authentication&Authorization
[https://docs.docker.com/ee/ucp/admin/configure/external-auth/](https://docs.docker.com/ee/ucp/admin/configure/external-auth/)

### How to ensure images pass security scans

