# Test docker

### Tester l'installation de docker 
```bash
docker run hello-world
```

### Creation de conteneur et utilisation de bash en interactif
```bash
docker run -it ubuntu bash
```

### Voir images disponible en local
```bash
docker images
```

### Voir liste des conteneurs 
```bash
docker ps -a
```

### Demarrer un serveur web 
```bash
docker run -p 80:80 nginx
```

### En arriere plan
```bash
docker run -d -p 80:80 nginx
```
