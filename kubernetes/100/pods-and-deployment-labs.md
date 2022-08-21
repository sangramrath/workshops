# WORK IN PROGRESS

## Creating and Managing deployments declaratively
mkdir nginx
cd nginx/
vi deployment.yaml
### Create deployment using YAML file (declarative)
```
kubectl apply -f deployment.yaml 
```
### Verify resources (deployments and pods) are created 
```
kubectl get deployments
kubectl get pods
```

kubectl describe pod web-6cb5f48868-6nz5m
kubectl events
kubectl get events 
kubectl logs web-6cb5f48868-6nz5m
kubectl logs web-6cb5f48868-6nz5m -c web
kubectl exec web-6cb5f48868-6nz5m -- /bin/sh
kubectl exec --tty web-6cb5f48868-6nz5m -- /bin/sh
kubectl exec --stdin --tty web-6cb5f48868-6nz5m -- /bin/sh
kubectl describe deployment web
kubectl get rs
 kubectl scale --replicas=2 rs/web-6cb5f48868
kubectl get pods
kubectl get rs
kubectl scale --replicas=2 deployment web
kubectl get pods
vi deployment.yaml 
kubectl apply -f deployment.yaml 
kubectl get pods
vi deployment.yaml 
kubectl apply -f deployment.yaml 
kubectl get pods
kubectl delete deployment web
kubectl run nginx --image:nginx --dry-run=client -o yaml > nginx.yaml
kubectl run nginx --image=nginx --dry-run=client -o yaml > nginx.yaml
vi nginx.yaml 
kubectl create deployment demodep01 --image=gcr.io/google-samples/kubernetes-bootcamp:v1 --dry-run=client -o yaml > bootcamp.yaml
vi bootcamp.yaml 
