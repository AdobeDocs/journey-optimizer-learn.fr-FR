---
title: Tester la solution
description: Créez une page web simple pour capturer des événements d’impression et de clic sur les offres.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18526
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 1%

---

# Tester la solution

## Déploiement des exemples de ressources

Si Node.js n’est pas installé, téléchargez-le et [installez-le ici](https://nodejs.org/)

Vérifiez l’installation en exécutant :

`node -v`

`npm -v`

## Configurer le dossier du projet

Créez un répertoire pour l’exemple d’application à l’aide des commandes suivantes :

`mkdir frequency-capping `

`cd frequency-capping `

## Initialiser le projet

`npm init -y`

## Installation des frameworks requis

`npm install express`

## Copier les fichiers de ressources

* Décompressez et placez le contenu de [server.zip](assets/server.zip) dans le dossier `frequency-capping`.
* Extrayez le contenu de [public.zip](assets/public.zip)dans le dossier &#39;frequency-capping&#39;

## Mettre à jour l’URL de la surface dans le fichier JavaScript

Ouvrez le `frequency-capping.js` situé dans le `public\scripts` et mettez à jour la propriété surfaces pour qu’elle corresponde à la configuration de canal utilisée dans la campagne

## Démarrer le nœud js server

Accédez au dossier `c:\frequency-capping` . Exécutez la commande `node server.js` pour démarrer le serveur JS de nœud sur le port 3000.


## Mise à jour de la propriété Adobe Experience Platform Tags

Ouvrez le fichier `frequency-capping.html` situé dans le dossier `public` dans l’éditeur de texte et remplacez la balise de script par la balise de script de votre propriété de balise Adobe Experience Platform créée à l’étape précédente de ce tutoriel. Veillez à enregistrer le fichier

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interaction avec les offres

* Ouvrez la [page web](http://localhost:3000) dans votre navigateur préféré.
* Interaction avec l’offre
* Actualiser la page
* Selon les règles de limitation de la fréquence, une nouvelle offre doit s’afficher

## Afficher le rapport

* Connexion à Journey Optimizer
* Accédez à Gestion des Parcours ->Campagnes
* Cliquez sur la campagne, puis sélectionnez le rapport approprié dans le menu Rapport .
