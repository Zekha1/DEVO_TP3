## Commandes utilisees

### Supprimer les ressources de l'exercice 3
kubectl delete deployment/guestbook-deployment service/guestbook-service \
	-n guestbook --ignore-not-found

### Config
helm lint .
helm template guestbook . --namespace guestbook

helm upgrade --install guestbook . \
	--namespace guestbook \
	--create-namespace

kubectl get deployments,pods,svc -n guestbook

### Modifier
helm upgrade guestbook . \
	--namespace guestbook \
	--set replicaCount=5

### Tester
kubectl port-forward -n guestbook svc/guestbook-service 3000:3000