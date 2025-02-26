# Utiliser une base de données dans un conteneur docker

### Récupération des images 
```bash
docker pull mysql:5.7
docker pull phpmyadmin/phpmyadmin
```

### Création du réseau
```bash
docker network create mysql-network
```

### On lance le conteneur MySQL
```bash
docker run --name mysql-container --network mysql-network -e MYSQL_ROOT_PASSWORD=mdp -d mysql:5.7
```

### On lance phpMyAdmin
```bash
docker run --name phpmyadmin-container --network mysql-network -d --link mysql-container:db -p 8080:80 phpmyadmin/phpmyadmin
```

### On va sur http://localhost:8080

### On se connecte
Serveur : db
Utilisateur : root
Mot de passe : mdp

### On crée une base qui s'appelle "mabase"

### On crée une table "utilisateurs" avec les colonnes suivantes
id (INT, auto-increment, clé primaire)

nom (VARCHAR(50))

email (VARCHAR(100))

![alt text](image.png)