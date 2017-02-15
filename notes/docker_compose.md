# Docker compse

Notes créées à partir du cours de tcoupin lien ci-dessous

## Sites utiles 
[Cours tcoupin](https://tcoupin.github.io/presentations/docker-compose/#/)  
[Doc compose](https://docs.docker.com/compose/reference/) 
[Doc install docker-compose](https://docs.docker.com/compose/install/)   

## Commandes utiles

### Lancer l’application avec la commande
```
docker-compose up [SERVICE]
```

### Gestion des conteneurs
```
docker-compose stop [SERVICE]  
docker-compose kill [SERVICE]  
docker-compose scale SERVICE=NB
```

### Nettoyage des conteneurs stoppés
```
docker-compose rm
```

### Nettoyage des éléments
```
docker-compose down
```

### Documentation
```
docker-compose help
```