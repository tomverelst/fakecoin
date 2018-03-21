FROM node:6.0.0

WORKDIR /usr/src/app

COPY package.json /usr/src/app/package.json
COPY package-lock.json /usr/src/app/package-lock.json
RUN npm install

COPY bin/ /usr/src/app/bin/
COPY public/ /usr/src/app/public/
COPY routes/ /usr/src/app/routes/
COPY server.js /usr/src/app/server.js

EXPOSE 3000

ENV RABBIT_URL amqp://rabbitmq:5672

CMD ["npm", "start"]