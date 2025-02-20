FROM node:18 AS build-front

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Utilisation de Nginx pour servir le contenu statique
FROM nginx:alpine AS prod-front
COPY --from=build-front /app/dist /usr/share/nginx/html

EXPOSE 80
ENTRYPOINT ["nginx", "-g", "daemon off;"]