FROM node:14

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install --only=production

COPY src/ .

EXPOSE 3000

CMD ["node", "index.js"]
