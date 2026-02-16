
FROM node:lts
WORKDIR /usr/src/app
COPY . .

RUN npm install express prom-client
CMD ["node", "index.js"]

EXPOSE 3000

