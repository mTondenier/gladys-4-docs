---
name: raspberry-pi
title: Raspberry Pi
permalink: "/en/installation"
lang: en
category: Installation
---

For this first Alpha of Gladys 4, we don't provide a pre-built Raspbian image.

We provide a Docker image which you can run on your Raspberry Pi easily.

### Install Docker on the Raspberry Pi

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
chmod u+x get-docker.sh
VERSION=18.06.3 ./get-docker.sh
```

### Start Gladys

```bash
docker run -d \
--privileged \
-p 80:1443 \
--network=host \
--name gladys \
-e NODE_ENV=production \
-e TZ=Europe/Paris \
-e SQLITE_FILE_PATH=/var/lib/gladysassistant/gladys-production.db \
-v /var/run/docker.sock:/var/run/docker.sock \
-v /var/lib/gladysassistant:/var/lib/gladysassistant \
-v /dev:/dev \
gladysassistant/gladys:4.0.0-alpha-arm
```

Note:

- `-e TZ=Europe/Paris` => Timezone used by container. Feel free to consult [this list](https://fr.wikipedia.org/wiki/List_of_tz_database_time_zones) on wikipedia if you need to change this value.

### Accessing Gladys

You can access Gladys directly by typing the IP of your Raspberry Pi in your browser. To find the IP, just type `ifconfig` on the Raspberry Pi shell, or you can use a network scanner app to find the IP ([Network Scanner](https://play.google.com/store/apps/details?id=com.easymobile.lan.scanner&hl=fr) on Android or [iNet](https://itunes.apple.com/fr/app/inet-network-scanner/id340793353?mt=8) on iOS)
