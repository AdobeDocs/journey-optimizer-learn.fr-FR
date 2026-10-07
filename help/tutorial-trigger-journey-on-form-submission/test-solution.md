---
title: Tester la solution
description: Créer un parcours pour envoyer un e-mail lors de l’envoi du formulaire
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00.000Z
jira: KT-20014
exl-id: 9b4a3e0c-d153-4a6b-a7de-b926bd669f6a
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
    internal-label: Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 1%
---
# Tester la solution


Tester la solution
>[!VIDEO](https://video.tv.adobe.com/v/3478546)

## Déploiement des exemples de ressources

Si Node.js n’est pas installé, téléchargez-le et [installez-le ici](https://nodejs.org/)

Vérifiez l’installation en exécutant :

`node -v`

`npm -v`

## Configurer le dossier du projet

Créez un répertoire pour l’exemple d’application à l’aide des commandes suivantes :

`mkdir trigger-journey `

`cd trigger-journey`

## Initialiser le projet

`npm init -y`

## Installation des frameworks requis

`npm install express dotenv axios cors`

## Copier les fichiers de ressources

* Décompressez et placez le contenu de [project-root.zip](assets/project-root.zip) dans le dossier `trigger-journey`.

* Créez un dossier appelé `public` dans le dossier `trigger-journey` .
* mettez à jour le fichier `.env` avec les valeurs appropriées. Ces valeurs sont disponibles à partir de la commande cURL téléchargée lors de la création de la connexion HTTP Source.
* Décompressez le contenu de [index.zip](assets/index.zip) dans le dossier `public` .

## Exécution du serveur

Vérifiez que vous vous trouvez dans le répertoire `trigger-journey`.
Exécuter la commande `node server.js`
Pointez votre navigateur sur [page web](http://localhost:3000/)
Remplissez et envoyez le formulaire. Le parcours est déclenché et un e-mail est envoyé à l’ID d’e-mail saisi dans le formulaire.
