FROM node:16.20-alpine AS builder

WORKDIR /app
RUN npm install -g @angular/cli@16.1.0

COPY ./package.json .
RUN npm install
COPY . .