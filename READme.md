



## Exécution Partie 1

Depuis la racine du projet :

`cd mini-projet-ansible/app-init` 

Puis :

`ansible-playbook -i hosts nginx_playbook.yaml` 

## ✅ Vérification après déploiement

`sur ton navigateur tu peux tout simplement saisir l´adresse IP de ton client Ansible  http://192.168.99.22:80 (remplacer ceci par l´adresse IP de ta machine cliente)  et tu veras cette page d´accueil que voici :` 


![Image](ansible_partie1.png)
# ✅ Exécution Partie 2

## 1️⃣ Aller dans le dossier

`cd mini-projet-ansible/app-template`

## 2️⃣ Lancer le playbook

`ansible-playbook -i hosts nginx_webapp_playbook.yaml` 


# ✅ Vérification après déploiement

``sur ton navigateur tu peux tout simplement saisir l´adresse IP de ton client Ansible  http://192.168.99.22:8080 (remplacer ceci par l´adresse IP de ta machine cliente)  et tu veras cette page d´accueil que voici :` 

![Image](ansible_partie2.png)
