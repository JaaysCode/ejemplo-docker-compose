# STAGE 1 -> Generar el bundle del código de Angular
FROM node:alpine AS build

WORKDIR /app

#Dependencias del proyecto

COPY package.json package-lock.json ./

RUN npm install
COPY . .
RUN npm run build


# Stage 2: Crear imagen sobre nginx

FROM nginx:alpine
COPY --from=build /app/dist/frontend/browser /usr/share/nginx/html
COPY nginx/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
