### STAGE 1: Build ###
FROM node:16.20.0 AS build
WORKDIR /usr/local/app
COPY package.json package-lock.json ./
RUN npm install -g @angular/cli@16.1.0
RUN npm install
COPY . .
RUN ng build

### STAGE 2: Run ###
FROM nginx:1.17.1-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /usr/local/app/dist/_nombre_del_proyecto /usr/share/nginx/html
EXPOSE 80