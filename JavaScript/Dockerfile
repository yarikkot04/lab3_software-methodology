FROM node:latest

WORKDIR /opt/application

COPY package.json package-lock.json /opt/application/

RUN npm ci

COPY . /opt/application

CMD [ "node", "index.js" ]