## Commandes utilisées

### Supprimer le pod
kubectl delete -f pod.yaml

### Forwarder le port
kubectl port-forward -n guestbook pod/guestbook-pod 3000:3000
 -n pour le namespace
=> le localhost:3000 du pc renvoie sur le port