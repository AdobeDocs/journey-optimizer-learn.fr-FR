---
title: Tester la solution
description: Créer un parcours pour envoyer un e-mail lors de l’envoi du formulaire
feature: Journeys
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-12-25T00:00:00Z
jira: KT-20014
source-git-commit: 6e773afb6bf1770467f9c02739e6b3ede29c81f4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

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
* Décompressez le contenu de [index.zip] dans le dossier public
* mettez à jour le fichier `.env` avec les valeurs appropriées. Ces valeurs sont disponibles à partir de la commande cURL téléchargée lors de la création de la connexion HTTP Source

## Exécution du serveur

Vérifiez que vous vous trouvez dans le répertoire `trigger-journey`.
Exécuter la commande `node server.js`
Pointez votre navigateur sur [page web](http://localhost:3000/)
Remplissez et envoyez le formulaire. Le parcours est déclenché et un e-mail est envoyé à l’ID d’e-mail saisi dans le formulaire.


