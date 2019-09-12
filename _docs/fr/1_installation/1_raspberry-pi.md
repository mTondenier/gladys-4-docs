---
name: raspberry-pi
title: Raspberry Pi
permalink: "/fr/installation"
lang: fr
category: Installation
---

Pour cette première Alpha de Gladys 4, nous ne fournissons pas d'image Raspbian, mais juste une image Docker.

### Installer Docker sur Raspberry Pi

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
chmod u+x get-docker.sh
VERSION=18.06.3 ./get-docker.sh
```

### Lancer Gladys

Pour lancer Gladys, exécutez la commande suivante sur votre Raspberry Pi:

```bash
docker run -d \
--restart=always \
--privileged \
--network=host \
--name gladys \
-e NODE_ENV=production \
-e SERVER_PORT=80 \
-e TZ=Europe/Paris \
-e SQLITE_FILE_PATH=/var/lib/gladysassistant/gladys-production.db \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /var/lib/gladysassistant:/var/lib/gladysassistant \
-v /dev:/dev \
gladysassistant/gladys:4.0.0-alpha-arm
```

Note:

- `-e TZ=Europe/Paris` => Pour changer le fuseau horaire du container, vous pouvez modifier cette variable. Vous trouverez toutes les valeurs possibles sur [cette list](https://fr.wikipedia.org/wiki/List_of_tz_database_time_zones).

### Accéder à Gladys

Vous pouvez accéder à Gladys en tapant l'IP de votre Raspberry Pi sur votre navigateur. Pour trouver l'IP de votre Raspberry Pi, vous pouvez utiliser des apps comme ([Network Scanner](https://play.google.com/store/apps/details?id=com.easymobile.lan.scanner&hl=fr) sur Android ou [iNet](https://itunes.apple.com/fr/app/inet-network-scanner/id340793353?mt=8) sur iOS)
