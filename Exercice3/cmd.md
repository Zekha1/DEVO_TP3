## Commandes utilisées

### Deployer le service
kubectl apply -f deployment.yaml

### Forwarder les ports
kubectl port-forward -n guestbook deployments/guestbook-deployment 3000:3000

### Supprimer un des pods
kubectl delete -n guestbook pods guestbook-deployment-648ffd7944-82dsv

ça supprime un et en relance un directement avec un autre nom (guestbook-deployment-648ffd7944-rsszn)