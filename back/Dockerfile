FROM node:18-alpine AS build-back

RUN apk update \
    && apk add --no-cache openssl\
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /var/cache/apk/*

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD [ "sh", "-c", "npx prisma db push && npm run start" ]
#CMD [ "npm", "run", "start" ]
