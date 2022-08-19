
## Pre-requisites - 1
### Set hostname for easier identification
```
sudo hostnamectl set-hostname worker01
```

### Logout and Login again
```
exit
```

## Pre-requisites - 2
### Update /etc/hosts. This is to resolve Hostname to IP Address.
```
sudo vi /etc/hosts
```

### Disable swap. Kubernetes has functionality issues with swap.
```
sudo swapoff -a
sudo sed -i '/ swap / s/^\(.*\)$/#\1/g' /etc/fstab
```

### Update host and install required packages
**apt-transport-https** is required for http/https capability in ubuntu repositories
```
sudo apt-get update && sudo apt-get install -y apt-transport-https curl
```

###  Add Kubernetes signing key 
```
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
```

###  Add Kubernetes Repo 
```
cat <<EOF | sudo tee /etc/apt/sources.list.d/kubernetes.list
deb https://apt.kubernetes.io/ kubernetes-xenial main
EOF
```

###  Update Node 
```
sudo apt update
```

## Install Kubernetes Tools
###  Install kubeadm, kubectl, kubelet
```
sudo apt-get install -y kubelet=1.23.0-00 kubeadm=1.23.0-00 kubectl=1.23.0-00
```

### Disable automatic updates to these packages
```
sudo apt-mark hold kubelet kubeadm kubectl
```

## Install Container Runtime i.e. containerd
### Enable bridge traffic to be seen by iptables
Create a containerd configuration file
```
cat <<EOF | sudo tee /etc/modules-load.d/containerd.conf
overlay
br_netfilter
EOF
```
Load required modules explicitly just to be sure
```
sudo modprobe overlay
sudo modprobe br_netfilter
```
Update systemctl configuration
```
cat <<EOF | sudo tee /etc/sysctl.d/99-kubernetes-cri.conf
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
net.bridge.bridge-nf-call-ip6tables = 1
EOF
```
Apply changes
```
sudo sysctl --system
```

### Install containerd
```
sudo apt-get update && sudo apt-get install -y containerd
```

### Create containerd configuration
```
sudo mkdir -p /etc/containerd
sudo containerd config default | sudo tee /etc/containerd/config.toml
```

### Restart and verify service is running
```
sudo systemctl restart containerd
sudo systemctl status containerd
```

## Kubernetes Installation
### Join Control Plane
```
sudo kubeadm join 172.31.0.199:6443 --token [token] --discovery-token-ca-cert-hash [sha]
```
NOTE Copy the above from control plane installation. Do not run it as it is.
