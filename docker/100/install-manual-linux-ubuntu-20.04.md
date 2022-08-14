# Installing Docker Engine (Server) on Ubuntu

## Pre-requisites
- Any VM / BM with Ubuntu installed

## Steps

### Update apt and install required packages  
```
sudo apt update
sudo apt install ca-certificates curl gnupg lsb-release curl git
```
Press "Y" when prompted for confirmation

### Add Official GPG Key & Repo
```
sudo mkdir -p /etc/apt/keyrings

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### Install Docker Engine, Containerd, Docker Compose(This installs the latest stable version)
```
sudo apt update

sudo apt install docker-ce docker-ce-cli containerd.io docker-compose docker-compose-plugin
```
Press "Y" when prompted for confirmation

### Run docker as a non-root user
```
sudo groupadd docker

sudo usermod -aG docker $USER
```

Logout from the VM/BM and log back in.

### Verify docker commands work
```
docker --version
```

## Reference
https://docs.docker.com/engine/install/ubuntu/
