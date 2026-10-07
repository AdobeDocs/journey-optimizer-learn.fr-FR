---
title: Tester la solution
description: Créez une page web simple pour capturer des événements d’impression et de clic sur les offres.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18526
exl-id: 6b6c66d3-218d-4f5b-adb0-a2eca05989ab
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%
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
