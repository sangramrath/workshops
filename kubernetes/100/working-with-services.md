
## Creating a Service of type NodePort
```
mkdir services
cd services
```
### Create a Deployment
```
wget https://raw.githubusercontent.com/sangramrath/workshops/main/kubernetes/100/dep-rs-nginx.yaml
kubectl apply -f dep-rs-nginx.yaml
kubectl get pods
```

### Create a Service
```
wget https://raw.githubusercontent.com/sangramrath/workshops/main/kubernetes/100/nodeport-svc.yaml
kubectl apply -f nodeport-svc.yaml
kubectl get svc
```

### Verify access from the web
Use the Public IP address of the Worker Node with the port from the svc to verify nginx web server is accessible from outside
