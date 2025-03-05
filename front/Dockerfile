FROM node:18-alpine AS build-front

RUN apk add --no-cache openssl

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Utilisation de Nginx pour servir le contenu statique
FROM nginx:alpine AS prod-front
COPY --from=build-front /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf