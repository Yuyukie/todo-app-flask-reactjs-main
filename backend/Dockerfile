# Utiliser une image officielle Python
FROM python:3.13-slim

# Définir le répertoire de travail
WORKDIR /app

# Copier le Pipfile et Pipfile.lock (si existants)
COPY Pipfile Pipfile.lock* ./ 

# Installer pipenv pour gérer les dépendances
RUN pip install pipenv

# Installer les dépendances à partir du Pipfile
RUN pipenv install --deploy --ignore-pipfile

# Copier tout le code source dans le conteneur
COPY . .

# Exposer le port utilisé par Flask
EXPOSE 5000

# Définir la commande pour démarrer l'application Flask
CMD ["pipenv", "run", "flask", "run", "--host=0.0.0.0"]