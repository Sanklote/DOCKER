# Test docker

### Tester l'installation de docker 
```
docker run hello-world
```

### Creation de conteneur et utilisation de bash en interactif
```
docker run -it ubuntu bash
```

### Voir images disponible en local
```
docker images
```

### Voir liste des conteneurs 
```
docker ps -a
```

### Demarrer un serveur web 
```
docker run -p 80:80 nginx
```

### En arriere plan
```
docker run -d -p 80:80 nginx
```
