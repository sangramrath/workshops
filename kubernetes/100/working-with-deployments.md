

## Upgrading, rollingback and scaling deployments
**NOTE: The following two steps may not be required if continuing for another lab. Check with instructor first.**

### Create a work directory
```
mkdir deployments
cd deployments
```

### Create a Deployment
```
wget https://raw.githubusercontent.com/sangramrath/workshops/main/kubernetes/100/dep-rs-nginx.yaml
kubectl apply -f dep-rs-nginx.yaml
kubectl get deployments
kubectl get pods
```

### Scale a deployment
#### Declarative method
```
vi dep-rs-nginx.yaml
```
Update the replicas to **5**, save and exit.
```
kubectl apply -f dep-rs-nginx.yaml
```
Check scaling status
```
kubectl get deployments
kubectl get pods
```
#### Imperative method
```
kubectl scale deployment/nginx-web --replicas=5
```

### Ugrade / Rollout a deployment
#### Declarative method
```
vi dep-rs-nginx.yaml
```
Update the image to **nginx:1.19.6**, save and exit
```
kubectl apply -f dep-rs-nginx.yaml
```
#### Imperative method
```
kubectl set image deployment/nginx-web nginx=nginx:1.19.6
```

### Check rollout details deployment
#### Rollout Status
```
kubectl rollout status deployment/nginx-web
```
#### Rollout History
```
kubectl rollout history deployment/nginx-web
```

### Rollback deployment
#### Perform another rollout, this time imperatively but deliberately making an error
```
kubectl set image deployment/nginx-web nginx=nginx:1.200
```
Check rollout status eventually finding out that the pods / deployment is in error
```
kubectl rollout status
kubectl get deployments
kubectl get pods
```
#### Undo rollout
```
kubectl rollout undo deployment/nginx-web
```
