# [[Docker]] install 
https://www.elastic.co/docs/deploy-manage/deploy/self-managed/install-elasticsearch-with-docker

# Multi-Node [[Cluster]]
We can have multiple nodes for **horizontal scalability** or **redundancy** and on the install we have a setup example 

## Walkthrough 

### .env 
In here we just have the variables we need to set

### [[Docker-compose||docker-compose.yml]]
``` 
esdata01:
	driver:local 
```
so the data is stored on the host
```
setup: #sets the certificates
es01-es03: #elastic search services
kibana: #kibana service
```

