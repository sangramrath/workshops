## Docker Information
### See system-wide information
```
docker info
```

## Container Operations
### View all running containers
```
docker ps
```

### View all containers
```
docker ps -a
```

### Run a container in attached mode (if the image i.e nginx is not available locally it downloads)
```
docker run nginx 
```

### Run a container in detached mode
```
docker run --detach nginx 
```
OR
```
docker run -d nginx
```

### Run a container, specify your own name
```
docker run -d --name demo_nginx nginx
```

### Stop a container
```
docker stop [container_id/container_name] 
```

### Start a container
```
docker start [container_id/container_name] 
```

### Remove a stopped container (if the container is not stopped, it throws an error)
```
docker rm [container_id/container_name]
```

### Remove a running container (BE CAREFUL with production containers)
```
docker rm [container_id/container_name] --force (or -f)
```

### Inspect a container (low-level)
```
docker inspect [container_id/container_name]
```

### Check container logs
```
docker logs [container_id/container_name]
```


## Image Operations
### View all images available locally
```
docker images
```

### Remove an image 
```
docker rmi [image_id/image_name] 
```

### Pull an image (from hub.docker.com)
```
docker pull [name:tag]
```
For example:
```
docker pull ubuntu:trusty
docker pull alpine
```

### See history of an image
```
docker history [image]
```
