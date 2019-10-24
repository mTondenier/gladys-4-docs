---
layout: docs
name: gateway-open-api
title: Configurer Owntracks avec Gladys Plus
category: Configuration
permalink: "/fr/configuration"
lang: fr
---

[Owntracks](https://owntracks.org/) est une application mobile open-source qui permet d'envoyer sa géolocalisation périodiquement à un serveur.

[Gladys Plus](https://gladysassistant.com/pricing) vous permet de recevoir ces localisations dans Gladys.

### Télécharger Owntracks

Tout d'abord, téléchargez Owntracks sur iOS ou Android.

### Créez une clé d'API dans Gladys Plus

Allez à [plus.gladysassistant.com](https://plus.gladysassistant.com/), connectez-vous.

Puis allez dans "settings" => "Open API", et créez une clé.

### Allez dans Owntracks

Clickez sur le bouton en haut à gauche de l'app:

<img src="/assets/image/configuration/gateway/open-api-owntracks-0.jpg" alt="Open API owntracks Gladys" class="img-responsive" width="300" />

Cliquez sur "paramètres":

<img src="/assets/image/configuration/gateway/open-api-owntracks-1.jpg" alt="Open API owntracks Gladys" class="img-responsive" width="300" />

Sélectionnez "HTTP", puis dans l'input "URL" entrez:

```
https://api.gladysgateway.com/v1/api/owntracks/[YOUR-API-KEY]
```

<img src="/assets/image/configuration/gateway/open-api-owntracks-2.jpg" alt="Open API owntracks Gladys" class="img-responsive" width="300" />

### Vérifier que l'intégration fonctionne

Dans Gladys, vous devriez voir votre position sur l'onglet "Maps".
