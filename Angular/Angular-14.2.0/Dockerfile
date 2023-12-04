FROM node:14.20.0 AS build
# Directorio de trabajo
WORKDIR /usr/src/app
COPY package.json package-lock.json ./
RUN npm install -g @angular/cli@14.2.0
RUN npm install
COPY . .