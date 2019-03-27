---
name: docker
title: Docker installation
permalink: "/en/installation"
lang: en
category: Installation
---

### Supported architectures

`amd64`, `arm32v6`, `arm64v8`, `i386`, `ppc64le`, `s390x`

### Supported tags

* `latest`
* `v4` (Major version)
* `v4.x.x` (Version)

### Gladys container

```shell
docker run --name gladys \
--restart=always \
-p 80:1444 \
-p 443:443 \
-e TZ=Europe/Paris \
-d gladysassistant/gladys:v4
```

Informations:

* `-p 80:1444` => Forwarding host port 80 to container port 1444, Gladys will be accessible from your browser on port 80 (default http port). 
* `-e TZ=Europe/Paris` => Timezone used by container. Feel free to consult [this list](https://fr.wikipedia.org/wiki/List_of_tz_database_time_zones) on wikipedia if you need to change this value.

### Accessing Gladys

To access Gladys, open your favorite browser, on any computer on the local network. Then enter the URL :

```
http://IP_OF_DOCKER_HOST
```

You should arrive on Gladys web interface where you can configure your account !