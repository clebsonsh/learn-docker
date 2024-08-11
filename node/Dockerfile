FROM node:22

USER node

WORKDIR /home/node/app

COPY --chown=node . .

RUN npm ci

CMD ["npm", "run", "start"]

