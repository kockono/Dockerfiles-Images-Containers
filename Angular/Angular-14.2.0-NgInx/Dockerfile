### STAGE 1: Build ###
FROM node:14.20.0 AS build
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install -g @angular/cli@14.2.0
RUN npm install
COPY . .
RUN ng build
EXPOSE 80


### STAGE 2: Run ###
# Copiar los certificados SSL
# COPY cert.pem /etc/nginx/cert.pem
# COPY key.pem /etc/nginx/key.pem

FROM nginx:1.17.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /usr/local/app/dist/name_project /usr/share/nginx/html
# Para HTTP
EXPOSE 80
# Para HTTPS
EXPOSE 443 