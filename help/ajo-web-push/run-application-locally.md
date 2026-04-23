---
title: Exécuter l’application localement
description: Configuration locale de l’exemple d’application pour explorer le flux de notifications push web à l’aide d’AJO.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 2635641b-5ae2-4303-bac7-02c3702950f0
source-git-commit: c339fe796af1e691cd3b1c98cd6ba8a8772551e4
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---

# Exécuter l’application localement

Cette page vous guide tout au long de la configuration locale de l’exemple d’application afin que vous puissiez tester et explorer le flux de notifications push web à l’aide de Adobe Journey Optimizer. Vous clonerez le référentiel, configurerez les variables d’environnement et exécuterez l’application sur votre système local.


Pour exécuter l’exemple d’application sur votre système local, procédez comme suit.

## &#x200B;1. Installez Node.js.

Vérifiez que **Node.js (version 16 ou ultérieure)** est installé sur votre système.

Vous pouvez le [télécharger ici :](https://nodejs.org/)

Vérification de l’installation

```node -v```

```npm -v```


## &#x200B;2. Clonez le référentiel

```git clone https://github.com/gbedekar489/ajo-web-push.git```

```cd ajo-web-push```

## &#x200B;3. Installer les dépendances

```npm install```

## &#x200B;4. Configuration Des Variables D’Environnement

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
