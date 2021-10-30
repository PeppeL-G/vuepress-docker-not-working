FROM node:lts-alpine

WORKDIR /vuepress-app

COPY ./package*.json ./
RUN npm install

COPY ./docs/ ./docs

RUN npm run docs:dev