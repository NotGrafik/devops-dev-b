FROM node:18 AS build-back

WORKDIR /app
COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD [ "sh", "-c", "npmx prisma db psuh && npm run start" ]
#CMD [ "npm", "run", "start" ]
