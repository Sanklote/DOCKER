# Dockerfile

### Faire le dockerfile

Pour installer les dépendence nécessaires :
```bash
RUN npm install --only=production
```

Pour le Dockerfile :

```bash
FROM node:14

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm install --only=production

COPY src/ .

EXPOSE 3000

CMD ["node", "index.js"]

```

### On crée on network
```bash
docker network create app-network
```

### On lance MySQL
```bash
docker run --name mysql-container --network app-network -e MYSQL_ROOT_PASSWORD=mdp -e MYSQL_DATABASE=db -p 3306:3306 -d mysql
```

### On build nodejs
```bash
docker build -t mon-app-nodejs .
```

### On lance js
```bash
docker run --name nodejs-container --network app-network -e DATABASE_HOST=mysql-container -e DATABASE_USER=root -e DATABASE_PASSWORD=mdp -e DATABASE_NAME=db -p 3000:3000 -d mon-app-nodejs
```


