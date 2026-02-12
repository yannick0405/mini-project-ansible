


## ⚠️ Remarque importante concernant les tests

Les deux parties du projet utilisent le port 80 du serveur.

- La Partie 1 installe Nginx directement sur le système (host) et occupe le port 80.
- La Partie 2 déploie Nginx dans un conteneur Docker et publie également le port 80.

⚠️ Il est donc impossible d'exécuter simultanément la Partie 1 et la Partie 2 sur le même serveur sans conflit de port.

Avant de tester la Partie 2, il est nécessaire d’arrêter Nginx installé lors de la Partie 1 :

```
bash
ansible -i hosts prod -b -m shell -a "systemctl stop nginx && systemctl disable nginx || true"

```

Ensuite, la Partie 2 peut être lancée normalement 


`ansible-playbook -i hosts nginx_webapp_playbook.yaml`



## Exécution Partie 1

Depuis la racine du projet :

`cd mini-projet-ansible/app-init` 

Puis :

`ansible-playbook -i hosts nginx_playbook.yaml` 

----------



----------

## ✅ Vérification après déploiement

`curl -I http://192.168.99.22` 

(Remplace par l’IP de ton client si différente.)

![Image](ansible_partie1.png)
# ✅ Exécution Partie 2

## 1️⃣ Aller dans le dossier

`cd mini-projet-ansible/app-template` 

----------

## 2️⃣ Lancer le playbook

`ansible-playbook -i hosts nginx_webapp_playbook.yaml` 

----------

# ⚠️ Important avant de lancer

Si la Partie 1 a été exécutée juste avant, il faut arrêter nginx du host :

`ansible -i hosts prod -b -m shell -a "systemctl stop nginx && systemctl disable nginx || true"` 

Sinon tu auras l’erreur :

`address already in use` 

----------

# ✅ Vérification après déploiement

`curl -I http://192.168.99.22`
![Image](ansible_partie2.png)
