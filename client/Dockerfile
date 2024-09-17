FROM node:14.21.3-alpine AS builder

# Ajouter le dépôt communautaire et installer Python 2
RUN echo "http://dl-cdn.alpinelinux.org/alpine/v3.12/main" >> /etc/apk/repositories && \
    echo "http://dl-cdn.alpinelinux.org/alpine/v3.12/community" >> /etc/apk/repositories && \
    apk update && \
    apk add --no-cache python2

WORKDIR /usr/src/app

COPY package*.json yarn.lock ./

RUN yarn install

COPY . .

RUN yarn build

LABEL authors="alexandre.messuves@gmail.com"

EXPOSE 3000

CMD ["yarn", "start"]