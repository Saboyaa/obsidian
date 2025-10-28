Docker is an open-source platform for automating the deployment of applications as self-contained units called containers. It uses a layered filesystem and resource isolation features to provide flexibility and portability. Additionally, it provides a robust set of tools for creating, deploying, and managing applications, which helps streamline the containerization process.
### Dockerfile example

```bash
# Use the latest Ubuntu 22.04 LTS as the base image
FROM ubuntu:22.04

# Update the package repository and install the required packages
RUN apt-get update && \
    apt-get install -y \
        apache2 \
        openssh-server \
        && \
    rm -rf /var/lib/apt/lists/*

# Create a new user called "docker-user"
RUN useradd -m docker-user && \
    echo "docker-user:password" | chpasswd

# Give the docker-user user full access to the Apache and SSH services
RUN chown -R docker-user:docker-user /var/www/html && \
    chown -R docker-user:docker-user /var/run/apache2 && \
    chown -R docker-user:docker-user /var/log/apache2 && \
    chown -R docker-user:docker-user /var/lock/apache2 && \
    usermod -aG sudo docker-user && \
    echo "docker-user ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

# Expose the required ports
EXPOSE 22 80

# Start the SSH and Apache services
CMD service ssh start && /usr/sbin/apache2ctl -D FOREGROUND
```

### Docker Run Syntax

```shell-session
docker run -p <host port>:<docker port> -d <docker container name>
```

## Docker Compose 

A way for [[Docker]] to load more than 1 service at the same time
#### Volumes: 
They are the persistence of the docker, basically mirrors the folder from your host to the container 
#### Networks:
Used for the container to talk with each other or other services
#### Services:
Defines the services of each container
```
services:
	image: #the image on DockerHub 
	build: #When you personalize a docker image creating a Dockerfile
	context: 
	depends on: # this service will only be loaded after the other 
		- other_service
	volumes:
		- host_path:docker_path
	ports:
		- host_port:docker_port
	
```