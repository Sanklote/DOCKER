# Docker compose

# On crée le fichier
```yml
version: '3.8'

services:
  db:
    image: mysql:8.0
    restart: always
    environment:
      MYSQL_DATABASE: mabase
      MYSQL_ROOT_PASSWORD: monmotdepasse
    ports:
      - '3306:3306'
    volumes:
      - db_data:/var/lib/mysql

  app:
    build: .
    ports:
      - '3000:3000'
    depends_on:
      - db
    environment:
      DATABASE_HOST: db
      DATABASE_PORT: 3306
      DATABASE_USERNAME: root
      DATABASE_PASSWORD: monmotdepasse
      DATABASE_NAME: mabase

volumes:
  db_data:
```

```bash
docker-compose -d
```
