#Usando alpine como imagen base para el node
FROM node:18.20.3-alpine

#Directorio de trabajo base para la aplicacion
WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

CMD ["node","app.js"]

