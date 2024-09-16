FROM node:14-alpine AS builder

WORKDIR /usr/src/app

COPY package*.json yarn.lock ./

RUN yarn --pure-lockfile

COPY . .

RUN yarn build

#FROM nginx:1.19.0-alpine

LABEL authors="alexandre.messuves@gmail.com"

#COPY --from=builder /usr/src/app/build /usr/share/nginx/html

#COPY default.conf /etc/nginx/conf.d/default.conf

#EXPOSE 80

CMD ["yarn", "start"]