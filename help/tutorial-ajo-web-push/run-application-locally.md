---
title: Exécuter l’application localement
description: Configuration locale de l’exemple d’application pour explorer le flux de notifications push web à l’aide d’AJO.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 2635641b-5ae2-4303-bac7-02c3702950f0
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%
---
# Exécuter l’application localement

Cette page vous guide tout au long de la configuration locale de l’exemple d’application afin que vous puissiez tester et explorer le flux de notifications push web à l’aide de Adobe Journey Optimizer. Vous clonerez le référentiel, configurerez les variables d’environnement et exécuterez l’application sur votre système local.


Pour exécuter l’exemple d’application sur votre système local, procédez comme suit.

## &#x200B;1. Installation de Node.js

Vérifiez que **Node.js (version 16 ou ultérieure)** est installé sur votre système.

Vous pouvez le [télécharger ici :](https://nodejs.org/)

Vérification de l’installation

`node -v`

`npm -v`


## &#x200B;2. Clonage du référentiel

`git clone https://github.com/gbedekar489/ajo-web-push.git`

`cd ajo-web-push`

## &#x200B;3. Installer les dépendances

`npm install`

## &#x200B;4. Configurer les variables d’environnement

Créez un fichier .env dans le répertoire racine et ajoutez les éléments suivants :

```
DATASTREAM_ID=your_datastream_id
ORG_ID=your_org_id
VAPID_PUBLIC_KEY=your_vapid_public_key
APP_ID=your_app_id
DATASET_ID=your_event_dataset_id
PORT=3000
```


Lors d’une exécution locale, ces valeurs sont lues à partir du fichier .env. En production (par exemple, Rendu), ils sont configurés en tant que variables d’environnement.
