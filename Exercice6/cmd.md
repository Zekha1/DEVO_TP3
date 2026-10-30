## Commandes utilisees

### Deployer Redis
kubectl create namespace
kubectl apply -f redis-deployment.yaml
kubectl apply -f redis-service.yaml

### Deployer le guestbook
helm lint .
helm upgrade --install guestbook . \
	--namespace guestbook \
	--create-namespace

### Tester sans Redis
kubectl scale deployment/redis -n data --replicas=0
kubectl get pods -n guestbook
kubectl describe pods -n guestbook
kubectl get events -n guestbook

### Remettre Redis
kubectl scale deployment/redis -n data --replicas=1
kubectl rollout status deployment/redis -n data
kubectl get pods -n guestbook

### Tester l'application
kubectl port-forward -n guestbook svc/guestbook-service 3000:3000
