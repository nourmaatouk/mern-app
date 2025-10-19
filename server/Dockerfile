# Utiliser une image Node légère
FROM node:lts-alpine

# Définir le dossier de travail
WORKDIR /app

# Copier les fichiers de dépendances
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste du code source
COPY . .

# Exposer le port du serveur
EXPOSE 9000

# Définir la variable d'environnement (optionnelle ici, mais utilisée via Compose)
ENV PORT=9000

# Démarrer le serveur
CMD ["npm", "start"]
