# Sujet

Sujet récupéré sur [le tp de tcoupin](https://github.com/tcoupin/tp_asi_ensg)

## Les TPs

Les 3 activités ont pour but de faire manipuler docker en mettant en pratique certains principes d'architecture des SI.

Le but est de mettre en place ownCloud, un gestionnaire de fichier en ligne en 3 étapes.

L'image à utiliser est `owncloud`, disponible sur https://hub.docker.com/r/library/owncloud/. Cette page contient beaucoup de détails que vous pouvez trouver dans les métadonnées de l'image.

### Owncloud SQLite : 2 Tiers

Un seul conteneur : owncloud et la base sqlite.

Utiliser l'option `--cpu-quota=25000` de `docker run` pour limiter l'utilisation du CPU à 25% et simuler des limites matérielles.

Notre solution est (artificiellement) lente, il faudrait la répartir sur plusieurs instances pour utiliser plus de ressources.

**Identifier les limites techniques.**

### Owncloud MySQL : 3 Tiers

La base de donnée doit être déportée dans une instance séparée. L'image à utiliser est `mysql` ou `mariadb`.

### Cluster Owncloud MySQL : distribution

Pour utiliser plus de ressources, on va déployer plusieurs instances owncloud derrière un répartiteur de charge.

Pour le répartiteur, vous avez le choix entre :

- nginx (config statique)
- haproxy (config statique)
- traefik (config statique ou dynamique)