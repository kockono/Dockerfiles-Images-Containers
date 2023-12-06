FROM node:16.20-alpine AS builder

WORKDIR /app
RUN npm install -g @angular/cli@16.1.0

COPY ./package.json .
RUN npm install
ENV GENERATE_SOURCEMAP=false
# Reached heap limit Allocation failed JavaScript heap out of memory
# RUN NODE_OPTIONS="--max-old-space-size=8192"
RUN node --max-old-space-size=16384
COPY . .

EXPOSE 4200
