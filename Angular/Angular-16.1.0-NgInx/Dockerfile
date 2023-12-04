### STAGE 1: Build ###
FROM node:16.20.0 AS build
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install -g @angular/cli@16.1.0
RUN npm install
COPY . .
RUN ng build

### STAGE 2: Run ###
FROM nginx:1.17.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /usr/src/app/dist/nombre-del-proyecto /usr/share/nginx/html