# Docker 

Notes créées à partir du cours de tcoupin lien ci-dessous

## Sites utiles 
[Play with docker](http://play-with-docker.com)  
[Hub docker](https://hub.docker.com/)  
[Cours tcoupin](https://tcoupin.github.io/presentations/docker-intro)  
[Command lines docker](https://docs.docker.com/engine/reference/commandline/docker/)  
[Dockerfiles doc](https://docs.docker.com/engine/reference/builder/)   

## Images

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

## CMD conteneur

### Démarrer un conteneur
```
docker run OPTIONS IMAGE[:TAG] COMMANDE
```

Exemple : 
```
docker run debian:jessie cat /etc/hostname
```

### Lister les conteneurs
```
docker ps
```

### Historique des conteneurs
```
docker ps -a
```

### Supprimer les conteneurs
```
docker rm "Nom_conteneur"
```

### Supprimer tous les conteneurs
```
docker rm $(docker ps -a -q)
```

#### Options utiles
* –name : donner un nom au conteneur  
* -i : interactif  
* -t : forcer l’allocation d’un TTY  
* –rm : supprimer le conteneur à la fin de son exécution  
* -d : démarrer le conteneur en arrière-plan  

### Gérer les conteneurs
* stop et start  
* retart  
* pause et unpause  

### Commiter un conteneur
```
docker commit CONTAINER_NAME IMAGE[:TAG]
```

## Réseau

### Pas de réseau
```
docker run --net none "Nom_conteneur"
```

### Réseau de l’hôte
```
docker run --net host "Nom_conteneur"
```

### Réseau isolé (par défaut)
```
docker run --net bridge "Nom_conteneur"
```

### Exposer un port avec l’option -p
```
docker run --rm -p PORT-HOTE:PORT-CONTENEUR httpd:alpine
```

## Volume
```
docker run -v LOCAL_PATH:PATH_ON_CONTAINER:MODE "Nom_conteneur"
```

## Volume docker

### Lister les volumes
```
docker volume ls
```

### Créer un volume
```
docker volume create --name NAME [OPTS]
```

### Créer un volume lors de la création d’un conteneur
```
docker run -v [NAME]:[PATH_ON_CONTAINER]:[OPTS] "Nom_conteneur"
```

### Supprimer un volume
```
docker volume rm NAME
```

### Supprimer un volume lors de la suppression d’un conteneur 

Ne concerne que les volumes créés automatiquement par les métadonnées d’une image.  

```
docker rm -v CONTAINER_NAME
```

## Dockerfiles

### Construire une image avec un Dockerfile
```
docker build DOCKERFILE_PATH
```

### Paramétriser le Dockerfile
```
docker build --build-arg name=value .
```

