# build stop
FROM node:22-alpine as build
WORKDIR /app
COPY  package*.json .
RUN npm ci
COPY  . .

# production step
FROM alpine:3.19
RUN apk add --update nodejs
RUN addgroup -S node && adduser -S node -G node
USER node
RUN mkdir /home/node/app
WORKDIR /home/node/app
COPY --from=build --chown=node:node /app .
CMD ["node", "server.js"]

