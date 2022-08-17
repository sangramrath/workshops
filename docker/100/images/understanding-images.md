
## Create Docker Hub account
1. Visit https://hub.docker.com/ and create a free account
2. Validate email if required and complete the sign-up process
3. Make a note of your dockerhub username

## Docker Image Operations
### Create folder and download start files
```
mkdir images
cd images
wget https://github.com/sangramrath/workshops/raw/main/docker/100/images/hello-world.py
wget https://github.com/sangramrath/workshops/raw/main/docker/100/images/Dockerfile
```

### Create image (hello-world is the name of the image)
```
docker build -t hello-world .
```

### Tagging an image
```
docker tag hello-world hello-world:v1
```

### Tagging an image for Docker Hub (replace [dockerhub_username] with actual username)
```
docker tag hello-world [dockerhub_username]/python-hello-world:v1
```

### Pushing an image to Docker Hub
```
docker login docker.io [dockerhub_username]
docker tag hello-world [dockerhub_username]/python-hello-world:v1
docker push [dockerhub_username]/python-hello-world:v1
```

### Make code change and rebuild again this time tagging the image directly during build process
```
vi hello-world.py
```
Make a small code change, save and exit (ESC > :wq)
```
docker build -t hello-world:v2 .
```

### Check image layer caching and new layers
```
docker history hello-world:v1
docker history hello-world:v2
```
