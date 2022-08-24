
## Run jenkins as a docker container
### Pre-requisites
Linux OS
Docker 
### Start a jenkins docker container
```
cd ~
mkdir jenkins
docker run -d --name jenkins -p 8080:8080 -v $PWD/jenkins/:/var/lib/jenkins jenkins/jenkins:lts-jdk11
docker logs jenkins
```
Make a note of the password provided
### Access Jenkins Dashboard
```
[PublicIP]:8080
```
When prompted enter the password copied earlier
