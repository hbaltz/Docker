# Docker 

## Sites utiles 
[Play with docker](http://play-with-docker.com)  
[Hub docker](https://hub.docker.com/)  
[Cours tcoupin](https://tcoupin.github.io/presentations/docker-intro) 

## CMD utiles

### Lister les images locales
```
docker images
```

### Chercher un dépoôt sur le hub
```
docker search "Nom_image"
```

### Télécharger une image depuis hub.docker.com
```
docker pull "Nom_image"
```

### Supprimer une image locale
```
docker rmi "Nom_image"
```

### Construire une image avec un Dockerfile
```
docker build "DOCKERFILE_PATH"
```

### (Re)Nommer/tagguer une image
```
docker tag IMAGE-NAME:TAG NEW_IMAGE-NAME:NEW_TAG
```

### Voir les métadonnées d’une image
```
docker inspect "Nom_image"
```