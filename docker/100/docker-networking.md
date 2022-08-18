
## Network Operations
### List all networks
```
docker network ls
```

### Inspect a network (here "bridge" is the network name)
```
docker network inspect brige
```

### Create a docker network
```
docker network create --driver bridge prod-net
```
Where "bridge" is the type of driver and "prod-net" is the network name

### Create a container and attach is to a specifc network
```
docker run -dit --name prod-alpine --network prod-net alpine ash
```

### Connect an existing container to a network
```
docker network connect prod-net db-alpine
```

### Remove a docker network
Ensure the network does not have any active endpoints (or containers using them)
```
docker network rm prod-net
```
