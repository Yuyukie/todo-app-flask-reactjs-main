# Étape 1 : Construire l'application avec Node.js et Vite
FROM node:18 AS build

# Définir le répertoire de travail
WORKDIR /app

# Copier les fichiers de configuration de dépendances
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste des fichiers de l'application
COPY . .

# Construire l'application avec Vite
RUN npm run build

# Étape 2 : Déployer l'application avec Nginx
FROM nginx:stable-alpine

# Copier les fichiers générés par Vite dans le répertoire de Nginx
COPY --from=build /app/dist /usr/share/nginx/html

# Exposer le port 80 de Nginx
EXPOSE 80