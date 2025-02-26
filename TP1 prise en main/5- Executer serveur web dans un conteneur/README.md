# Executer serveur web dans un conteneur 

### Récupérer l’image sur le Docker Hub
```bash
docker pull nginx
```

### Vérifier que cette image est présente en local
```bash
docker images
```

### On vient y mettre une page html test
```bash
echo "<html><body><h1>Ma page html</h1></body></html>" > index.html
```

### Démarrer un conteneur et servir la page html créée précédemment à l’aide d’un volume (option -v de docker run)
```bash
docker run -d -p 8080:80 -v $(pwd)/index.html:/usr/share/nginx/html/index.html nginx
```

### Supprimer le conteneur précédent et arriver au même résultat que précédemment à l’aide de la commande docker cp
Supprimer l'ancien conteneur 
```bash
docker stop nginx
```

```bash
docker rm nginx
```
Lancer un conteneur sans volume
```bash
docker run -d -p 8080:80 --name mon_nginx nginx
```
Copier le fichier dans le conteneur
```bash 
docker cp index.html mon_nginx:/usr/share/nginx/html/index.html
```
