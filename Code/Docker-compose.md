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