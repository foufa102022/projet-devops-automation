# Utilisez une image de base Node.js
FROM node:14
# MÉTADONNÉES DE L'IMAGE
LABEL version="1.0" maintainer="CHETOUI IFTIKHAR <chetouiiftikhar@gmail.com>"
# Définissez le répertoire de travail
WORKDIR /app

# Copiez les fichiers du projet dans le conteneur
COPY api/package*.json ./
COPY api/ .

# Installez les dépendances
RUN npm install

# Exposez le port sur lequel votre application Node.js écoute
EXPOSE 3080


# Commande pour démarrer l'application
CMD ["npm", "start"]
