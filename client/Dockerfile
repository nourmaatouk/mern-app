# Étape 1 : Build de l’application React
FROM node:lts-alpine AS build

WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

# Étape 2 : Servir l’application avec un serveur léger
FROM node:lts-alpine

WORKDIR /app
RUN npm install -g serve

# Copier le dossier build depuis l’étape précédente
COPY --from=build /app/build ./build

EXPOSE 3000

CMD ["serve", "-s", "build", "-l", "3000"]
