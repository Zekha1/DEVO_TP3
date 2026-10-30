## Commandes utilisees

### Installer Ingress
minikube addons enable ingress

### Redeployer Redis
kubectl create namespace data --dry-run=client -o yaml | kubectl apply -f -
kubectl apply -f redis-deployment.yaml
kubectl apply -f redis-service.yaml

### Redeployer le guestbook
helm lint .
helm upgrade --install guestbook . \
	--namespace guestbook \
	--create-namespace

### Verifier
kubectl get ingress -n guestbook
kubectl get pods,svc -n guestbook

### Tester avec le navigateur
echo "$(minikube ip) guestbook.local" | sudo tee -a /etc/hosts

Ouvrir le navigateur :
http://guestbook.local

### Desactiver l'Ingress
helm upgrade guestbook . \
	--namespace guestbook \
	--set ingress.enabled=false
