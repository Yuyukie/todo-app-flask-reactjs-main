Ce projet est une application web dockerisée utilisant React (frontend), Flask (backend), MySQL (base de données), PhpMyAdmin (gestion de base de données) et Nginx (reverse proxy). 

Suivez les étapes ci-dessous pour configurer et exécuter ce projet dans un nouvel environnement.

Prérequis
Avant de commencer, assurez-vous d'avoir les outils suivants installés sur votre machine :

Docker : Installez Docker depuis le site officiel.
Docker Compose : Inclus avec la plupart des installations de Docker, ou téléchargez-le depuis Docker Compose.


Structure du Projet

Voici l'organisation des fichiers du projet :

bash
Copier le code
.
├── docker-compose.yml         # Orchestre tous les services
├── Nginx/
│   └── Dockerfile             # Fichier Docker pour Nginx
├── backend/
│   ├── Dockerfile             # Fichier Docker pour le backend Flask
│   └── ...                    # Code du backend
├── frontend/
│   ├── Dockerfile             # Fichier Docker pour le frontend React
│   └── ...                    # Code du frontend
├── .env                       # Variables d'environnement (facultatif)
└── db_data/                   # Volume pour la persistance des données MySQL

Démarrage

1. Cloner le Dépôt

git clone https://github.com/votre-repo/todo-app-flask-reactjs.git
cd todo-app-flask-reactjs

2. Configurer les Variables d’Environnement

Assurez-vous que les variables d’environnement suivantes sont configurées dans votre fichier .env (facultatif) :

FLASK_ENV : development
DATABASE_URL : mysql://user:password@db_tp_docker/mydatabase
VITE_API_URL : http://localhost/api

Ces valeurs sont déjà définies dans le fichier docker-compose.yml pour un environnement de développement local.

3. Construire et Lancer les Conteneurs

Exécutez la commande suivante pour construire et démarrer tous les services :

docker-compose up --build

4. Accéder à l’Application

Une fois les conteneurs démarrés, vous pouvez accéder aux services via les URLs suivantes :

Service	URL
Frontend	http://localhost:3000
Backend (API)	http://localhost:5000
PhpMyAdmin	http://localhost:8080
Nginx (Proxy)	http://localhost
