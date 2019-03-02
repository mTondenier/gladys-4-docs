---
name: docker
title: Installation Docker
permalink: "/fr/installation"
lang: fr
category: Installation
---

### Architectures supportées

`amd64`, `arm32v6`, `arm64v8`, `i386`, `ppc64le`, `s390x`

### Tags disponible

* `latest`
* `v3` (Version majeure)
* `v3.x.x` (Version spécifique)

### Création du conteneur Maria DB

```shell
docker run --name gladys-mariadb \
--restart=always \
-e MYSQL_ROOT_PASSWORD=mysecretpassword \
-e MYSQL_DATABASE=gladys \
-d mariadb:latest \
--character-set-server=utf8mb4 \
--collation-server=utf8mb4_general_ci
```

Explications:

* `--restart=always` => nous voulons que si le container/la machine crash, il redémarre automatiquement
* `-v /var/lib/mysql:/var/lib/mysql` => Ici, nous montons un volume au container afin que les fichiers enregistrés par MariaDB soit enregistrés sur la machine "parente". Car lorsqu'un container est mis à jour/relancé, tout son contenu est supprimé, il ne faut rien enregistrer dans un container Docker ! Du coup ici les données MariaDB seront préservées même en cas de suppression du container.
* `-e MYSQL_ROOT_PASSWORD=mysecretpassword` et `-e MYSQL_DATABASE=gladys` => on spécifie ici les variables d'environnements qui seront lues par MariaDB pour définir le mot de passe root et le nom de la base de donnée.
* `-d` => L'option '-d' signifie 'detached', c'est à dire que le container va tourner en arrière-plan.

### Initialisation de la base de données

```shell
docker run --rm \
-e NODE_ENV=development \
-e MYSQL_HOST=mariadb \
-e MYSQL_PASSWORD=mysecretpassword \
-e MYSQL_PORT=3306 \
-e TZ=Europe/Paris \
--link gladys-mariadb:mariadb \
gladysproject/gladys:v3 \
node init.js
```

Explications:

Ce conteneur ne sert qu'à initialiser la base de données, le script `init.js` de Gladys s'occupe de créer le schéma.

### Création du conteneur Gladys

```shell
docker run --name gladys-node \
--restart=always \
-p 80:8080 \
-e NODE_ENV=production \
-e MYSQL_HOST=mariadb \
-e MYSQL_PASSWORD=mysecretpassword \
-e MYSQL_PORT=3306 \
-e TZ=Europe/Paris \
--link gladys-mariadb:mariadb \
-d gladysproject/gladys:v3
```

Explications:

* `-p 80:8080` => On map le port 80 de l'hôte au port 8080 du container, pour pouvoir accéder à Gladys depuis notre navigateur sur le port 80. 
* `-e TZ=Europe/Paris` => On définit le fuseau horaire qu'utilisera le conteneur. Vous pouvez consulter [cette liste](https://fr.wikipedia.org/wiki/List_of_tz_database_time_zones) sur wikipédia si vous ne savez quelle valeur renseigner.

### Accéder à Gladys

Rendez-vous sur votre navigateur internet sur n'importe quelle machine présente sur le réseau local. Puis accèdez à l'URL :


```
http://IP_HOTE_DOCKER
```

Vous devriez arriver sur l'interface de Gladys. Vous pouvez désormais configurer votre compte !