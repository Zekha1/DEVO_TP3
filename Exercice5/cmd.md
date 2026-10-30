## Commandes utilisees

### Deployer Redis
kubectl create namespace data
kubectl apply -f redis-pvc.yaml
kubectl apply -f redis-deployment.yaml
kubectl apply -f redis-service.yaml

### Verifier Redis
kubectl get pods,svc,pvc -n data

### Deployer le guestbook
helm lint .
helm template guestbook . --namespace guestbook
helm upgrade --install guestbook . \
	--namespace guestbook \
	--create-namespace

kubectl get deployments,pods,svc,configmap -n guestbook

### Modifier
helm upgrade guestbook . \
	--namespace guestbook \
	--set redisHost=redis.data.svc.cluster.local

### Tester
kubectl port-forward -n guestbook svc/guestbook-service 3000:3000
