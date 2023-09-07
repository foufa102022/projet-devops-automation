                        # --------------- DÉBUT COUCHE OS -------------------
FROM node:14-slim
# --------------- FIN COUCHE OS ---------------------

# MÉTADONNÉES DE L'IMAGE
LABEL version="1.0" maintainer="CHETOUI IFTIKHAR <chetouiiftikhar@gmail.com>"



# VARIABLES TEMPORAIRES
ARG NODE_PORT="3000"
# Créez un répertoire de travail dans le conteneur
                                 
WORKDIR /app

# Copiez les fichiers package.json et package-lock.json (ou yarn.lock si vous u>
COPY ui/package*.json ./

# Installez les dépendances du projet
RUN npm install

# Copiez le reste de votre application
COPY /ui .

# OUVERTURE DU PORT sur lequel le serveur de développement de React s'exécute 
EXPOSE ${NODE_PORT}
#LES COMMANDES QUI SERONT EXÉCUTÉ LORS DU LANCEMENT DU CONTENAIRE demarrage de >
CMD ["npm" , "start"]
