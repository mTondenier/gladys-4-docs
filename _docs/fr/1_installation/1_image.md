---
name: image
title: Installation clé en main
permalink: "/fr/installation"
lang: fr
category: Installation
---

Parce qu'une vidéo est toujours plus explicite, n'hésitez pas à regarder le tutoriel vidéo!

<div class="embed-responsive embed-responsive-16by9">
<iframe width="560" height="315" src="https://www.youtube.com/embed/rx1PmlMGh38" frameborder="0" allowfullscreen=""></iframe>
</div>

Pour installer Gladys sur un Raspberry Pi, vous pouvez cloner l’image Raspbian pré-conçue pour Raspberry Pi directement sur votre carte SD !

La première étape, c'est de télécharger l'image Raspbian.

Vous pouvez télécharger l'image Raspbian sur GitHub => [Télécharger l'image Raspbian Gladys sur GitHub](https://bit.ly/gladys-3-8-0-rev2)

Si le téléchargement est lent sur GitHub ou ne fonctionne pas, vous pouvez télécharger l'image sur le miroir officiel Gladys => [Télécharger l'image Raspbian Gladys sur le miroir officiel](https://bit.ly/gladys-3-8-0-rev2-mirror-fr2)

L'image Raspbian est compressée dans un fichier zip, que vous devez dézipper afin d'arriver à un fichier ".img".

L'étape d'après est de cloner l'image Raspbian Gladys sur la carte SD (c'est très simple), de la même manière que l'on clone l'image Raspbian "originale" sur un Raspberry Pi.

Je vous conseille pour cela le super tool [Etcher](https://etcher.io/) (compatible Linux/MacOS/Windows).

Installez Etcher, branchez votre carte SD à votre ordinateur, et clonez le fichier .img sur la carte.


<img src="/assets/image/installation/etcher.png" alt="Etcher Gladys carte SD Raspberry Pi" class="img-responsive" />

Ensuite, vous pouvez brancher votre Raspberry Pi en Ethernet à votre box, et le brancher sur le secteur. Une petite étape supplémentaire est nécessaire, il faut maintenant étendre la partition sur le Raspberry Pi pour que l'image prenne la taille de votre carte SD. Si vous n'étendez pas la partition, votre image ne prendra pas parti de toute la taille disponible sur votre carte SD, et vous allez vite manquer d'espace disque !

Pour cela, deux options : se connecter sur le Raspberry Pi directement ( avec un clavier et un écran branché en HDMI ), ou en SSH. Je vous conseille le SSH, beaucoup plus simple à mettre en place. Pour se connecter en SSH, il y a plein de tutoriels disponibles, pour [Windows](https://www.raspberrypi.org/documentation/remote-access/ssh/windows.md) et [Mac/Linux](https://www.raspberrypi.org/documentation/remote-access/ssh/unix.md).

Le compte sur le Raspberry Pi est celui par défaut (user : pi, mot de passe : raspberry).

Une fois connecté en ligne de commande sur le Raspberry Pi, il faut juste taper la commande:

    sudo raspi-config

Et sélectionner l'option "1\. Expand Filesystem". Le système va vous proposer de rebooter, il faut le faire afin de prendre en compte la modification.

Et c'est tout ! Gladys est prête, et tourne déjà :)

### Accéder à Gladys

Pour accéder à Gladys, c'est très simple. Rendez-vous sur votre navigateur internet sur n'importe quelle machine présente sur le réseau local où tourne le Raspberry Pi (que la machine soit en Wi-Fi, Ethernet, il suffit juste qu'elle soit connectée à la même box que le Raspberry Pi)

Puis tapez l'URL :

    http://gladys.local

Vous devriez arriver sur l'interface de Gladys. Vous pouvez désormais configurer votre compte :)

**Note :** Si cela ne marche pas, pas de panique. Vous pouvez taper directement l'IP de votre Raspberry Pi dans la barre de votre navigateur. Pour trouver l'IP du Raspberry Pi, vous pouvez soit taper `ifconfig` en ligne de commande sur le Rpi, ou alors utiliser des outils de scan réseaux pour trouver son IP ([Network Scanner](https://play.google.com/store/apps/details?id=com.easymobile.lan.scanner&hl=fr) sur Android par exemple, ou [iNet](https://itunes.apple.com/fr/app/inet-network-scanner/id340793353?mt=8) sur iOS)

**Note 2:** Si vous avez un quelconque problème lors de l'installation, n'hésitez pas à venir en parler sur le [forum Gladys](https://community.gladysassistant.com/), en général quelqu'un vous répondra assez rapidement !