#

### Création du Dockerfile
```bash
mkdir 6-builder_une_image
cd 6-builder_une_image
nano Dockerfile
```

### Editer Dockerfile
```bash
FROM nginx:latest
COPY index.html /usr/share/nginx/html/index.html

```

### Créer index.html
```bash
echo "<html><body><h1>Ma page html</h1></body></html>" > index.html
```

### Build le conteneur
```bash
docker build -t mon-serveur-web:v1 .
```

### Lancer le conteneur
```bash
docker run -d -p 8080:80 mon-serveur-web:v1
```

# On peut constater que les commandes sont moins nombreuses et moins compliquée car elles sont présentent directement dans le Dockerfile

# Il est plus facile ainsi de reproduire un conteneur similaire
# Plus facile à automatiser 