# Initialisation 
```bash
npx create-react-app .
```

```bash
npm start
```

Vérifier en allant sur  http://localhost:3000

### Faire le dockerfile

```bash
FROM node:18-alpine as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
```

```bash
docker build -t react-docker-app .
docker run -p 3000:80 react-docker-app
```

Ouvrez http://localhost:3000