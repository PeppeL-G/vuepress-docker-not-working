FROM node:14.15.1

WORKDIR /vuepress-app

COPY ./package*.json ./
RUN npm install

COPY ./docs/ ./docs

RUN npm run docs:dev