# Commande :

## Lancement normal
```
docker run -d -p 8080:80 owncloud
```

## Lancement cpu limité 25%
```
docker run --name owncloud --cpu-quota=25000 -d -p 8080:80 owncloud
```

## Observations :

Lors de la limite extrêment lent, limite technique
Multinstance impossible