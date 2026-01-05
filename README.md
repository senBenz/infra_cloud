

📊 Projet Cloud Zabbix – Supervision & Monitoring

🧠 Présentation du projet

Ce projet consiste à mettre en place une solution de supervision centralisée avec Zabbix dans un environnement cloud / virtualisé.
L’objectif est de surveiller en temps réel les serveurs et services, détecter rapidement les incidents et visualiser les performances du système.

La solution est conçue pour être scalable, fiable et adaptée aux infrastructures cloud.

⸻

🎯 Objectifs du projet
	•	Déployer un serveur de supervision Zabbix
	•	Superviser des machines virtuelles / serveurs Linux
	•	Collecter les métriques :
	•	CPU
	•	Mémoire (RAM)
	•	Disque
	•	Réseau
	•	Configurer des alertes et des déclencheurs (triggers)
	•	Fournir une interface Web de monitoring
	•	Utiliser une architecture cloud basée sur Docker

⸻

🏗️ Architecture générale

L’architecture du projet est composée des éléments suivants :
	•	Zabbix Server : collecte et traite les données de supervision
	•	Zabbix Agent 2 : installé sur les machines à superviser
	•	Base de données MySQL : stockage des données
	•	Interface Web Zabbix (incluse dans l’image officielle Zabbix)
	•	Docker & Docker Compose pour le déploiement

<img width="928" height="535" alt="Structure" src="https://github.com/user-attachments/assets/cebaad5d-8690-443c-86d6-aa538d16ff9f" />


⸻

🛠️ Technologies utilisées
	•	Zabbix (Server & Agent 2)
	•	Docker
	•	Docker Compose
	•	MySQL
	•	Linux (Ubuntu Server)


⸻

🚀 Déploiement du projet

1️⃣ Prérequis
	•	Linux (Ubuntu recommandé)
	•	Docker installé
	•	Docker Compose installé
	•	Accès root ou sudo

⸻

2️⃣ Lancement des conteneurs Zabbix

Dans le dossier du projet :

docker-compose up -d

Vérification des conteneurs :

docker ps


⸻

3️⃣ Accès à l’interface Web Zabbix

Ouvrir un navigateur et accéder à :

http://IP_DU_SERVEUR:8080

Identifiants par défaut :
	•	Utilisateur : Admin
	•	Mot de passe : zabbix

⸻

🖥️ Configuration des agents Zabbix

Sur chaque machine à superviser :

Installation de l’agent

sudo apt update
sudo apt install zabbix-agent2 -y

Configuration principale

Fichier :

/etc/zabbix/zabbix_agent2.conf

Paramètres importants :

Server=IP_ZABBIX_SERVER
ServerActive=IP_ZABBIX_SERVER
Hostname=VM-CLIENT-01

Redémarrage de l’agent :

sudo systemctl restart zabbix-agent2
sudo systemctl enable zabbix-agent2


⸻

🔐 Ports réseau utilisés

Service	Port	Description
Zabbix Server	10051	Collecte des données
Zabbix Agent	10050	Envoi des métriques
Interface Web	8080	Accès au monitoring


⸻

📈 Supervision & fonctionnalités
	•	Surveillance des ressources système
	•	Détection automatique des hôtes
	•	Tableaux de bord dynamiques
	•	Alertes en temps réel
	•	Historique et tendances des performances

⸻

🧪 Tests réalisés
	•	Test de connectivité Agent ↔ Server
	•	Surveillance CPU / RAM / Disque
	•	Génération d’alertes en cas de surcharge
	•	Visualisation des métriques en temps réel

⸻

🔒 Sécurité
	•	Accès contrôlé à l’interface Web
	•	Communication Agent ↔ Server limitée par IP
	•	Ports exposés strictement nécessaires

⸻

🧾 Conclusion

Ce projet démontre la mise en place d’une solution de supervision cloud complète avec Zabbix, permettant une gestion proactive des infrastructures.
Il constitue une base solide pour des environnements professionnels et académiques.

⸻

👤 Auteur

Saad Aaqil
Étudiant en ingénierie informatique
Projet académique – Supervision Cloud avec Zabbix

