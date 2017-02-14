# Docker 

## Sites utiles 
[http://play-with-docker.com](http://play-with-docker.com)  
[https://hub.docker.com/](https://hub.docker.com/) 
[https://tcoupin.github.io/presentations/docker-intro](https://tcoupin.github.io/presentations/docker-intro) 

## CMD 

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