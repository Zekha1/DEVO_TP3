# Apprentissages TP3

## 0. Préparer votre environnement

Installer toutes les dépendances.

### Problème rencontré et pourquoi il est survenu
Problème au lancement de minikube à cause de Docker puis de kvm puis des groupes..............

### Solution appliquée et pourquoi cette solution fonctionne
Déactiver Docker, installer libvirt, changer les groupes, reboot le PC...

### Ce que j'ai appris
Docker Desktop sur Debian c'est nul, reboot le pc en cas de problème c'est LA solution.

---

## 1. Explorer minikube et les bases de Kubernetes

Créer des namespaces, afficher les détails des noeuds.

### Problème rencontré et pourquoi il est survenu
Aucun problème.

### Solution appliquée et pourquoi cette solution fonctionne
NA

### Ce que j'ai appris
Créer des namespaces et afficher les détails.

---

## 2. Déployer le guestbook (Pod)

Mettre une image docker dans un pod.

### Problème rencontré et pourquoi il est survenu
Image non trouvée, impossible de l'ajouter. Oublié le port, suppression pour refaire.

### Solution appliquée et pourquoi cette solution fonctionne
Il fallait lancer le processus de Docker pour qu'il trouve l'image. Commande "kubectl delete -f pod.yaml".

### Ce que j'ai appris
Mettre une image docker dans un pod avec la commande "minikube image load guestbook:v0.1.0" et avec le yaml. Supprimer un pod.

---

## 3. Déployer le guestbook (Deployment + Service)

Utiliser un deployment pour relancer les pods automatiquement en cas de problème.

### Problème rencontré et pourquoi il est survenu
J'ai eu un peu de mal à trouver comment supprimer un seul des pods.

### Solution appliquée et pourquoi cette solution fonctionne
kubectl delete -n guestbook pods guestbook-deployment-648ffd7944-82dsv ça va bien chercher dans le namespace guestbook et le pod dont le nom précis est celui là.

### Ce que j'ai appris
Créer un deployment.yaml, cibler un pod dans un déploiement pour le supprimer.

---

## 4. Déployer le guestbook (Helm Chart)

### Problème rencontré et pourquoi il est survenu

### Solution appliquée et pourquoi cette solution fonctionne

### Ce que j'ai appris

---

## 5. Ajouter une base de données (Redis)

### Problème rencontré et pourquoi il est survenu

### Solution appliquée et pourquoi cette solution fonctionne

### Ce que j'ai appris

---

## 6. Rendre l'application robuste avec les probes

### Problème rencontré et pourquoi il est survenu

### Solution appliquée et pourquoi cette solution fonctionne

### Ce que j'ai appris

---

en +

## 7. Exposer le guestbook avec un Ingress

### Problème rencontré et pourquoi il est survenu

### Solution appliquée et pourquoi cette solution fonctionne

### Ce que j'ai appris

---

## 8. Faire monter en charge automatiquement (HPA)

### Problème rencontré et pourquoi il est survenu

### Solution appliquée et pourquoi cette solution fonctionne

### Ce que j'ai appris

---

## 9. Gérer deux environnements

### Problème rencontré et pourquoi il est survenu

### Solution appliquée et pourquoi cette solution fonctionne

### Ce que j'ai appris

---

## 10. Sauvegarder Redis avec un CronJob

### Problème rencontré et pourquoi il est survenu

### Solution appliquée et pourquoi cette solution fonctionne

### Ce que j'ai appris