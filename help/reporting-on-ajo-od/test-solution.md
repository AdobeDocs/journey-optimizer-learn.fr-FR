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
source-git-commit: 69bc8aace3cc502a18e691584824176833413c7e
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---

# Tester la solution

Pour tester la solution de bout en bout, les fichiers [weather-offers.html](assets/weather-offers.html) et [capture-impressions-click-events.js](assets/capture-impressions-click-events.js) doivent être hébergés sur un serveur web ou un service d’hébergement public tel que Github Pages. Cela est nécessaire, car l’API de géolocalisation du navigateur ne fonctionne que via HTTPS ou localhost

## Télécharger les fichiers fournis

[Fichier HTML](assets/weather-offers.html)

[Fichier JavaScript](assets/capture-impressions-click-events.js)

## Mettre à jour l’URL de la surface dans le fichier JavaScript

Ouvrez le `capture-impressions-click-events.js` et mettez à jour le ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`en remplaçant `yourdomain.com` par le domaine réel dans lequel le fichier HTML est hébergé.


## Mise à jour de la propriété Adobe Experience Platform Tags

Ouvrez le fichier weather-offers.html dans l’éditeur de texte et remplacez la balise de script par la balise de script de votre propriété de balise Adobe Experience Platform créée à l’étape précédente de ce tutoriel. Veillez à enregistrer le fichier

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```

## Interaction avec les offres

- Ouvrez la page web dans votre navigateur préféré.

- Autoriser le _**suivi de l’emplacement**_. Cela est nécessaire pour obtenir les détails météorologiques en fonction de votre emplacement.

- Cliquez sur le bouton dans les offres pour déclencher l’événement d’interaction.

## Afficher le rapport

- Connexion à Journey Optimizer

- Accédez à Gestion des Parcours ->Campagnes

- Cliquez sur la campagne, puis sélectionnez le rapport approprié dans le menu Rapport .
