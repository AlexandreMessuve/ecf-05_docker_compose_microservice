FROM node:14-alpine AS builder

WORKDIR /usr/src/app

COPY package*.json yarn.lock ./

RUN yarn install

COPY . .

RUN yarn build

LABEL authors="alexandre.messuves@gmail.com"

EXPOSE 3000

CMD ["yarn", "start"]