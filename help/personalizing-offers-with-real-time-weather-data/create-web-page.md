---
title: Tester la solution
description: Créez une page web simple pour tester la personnalisation contextuelle de l’offre à l’aide des données de température en temps réel.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 609a5ddf-d6c6-4f19-bd7f-bca8c266b759
source-git-commit: 9c11ebd2e52de18792e9fa135db955eeeb243673
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Tester la solution

Pour tester la solution de bout en bout, les fichiers [weather-offers.html](assets/weather-offers.html) et [weather-related-offers-script.js](assets/weather-related-offers-script.js) doivent être hébergés sur un serveur web ou un service d’hébergement public tel que Github Pages. Cela est nécessaire car :
- L’API de géolocalisation du navigateur ne fonctionne qu’avec HTTPS ou localhost

Pour assurer l’organisation et le bon fonctionnement des chemins d’accès relatifs, nous vous recommandons la structure de dossiers suivante pour héberger la solution :

![structure-dossier](assets/folder-structure.png)

## Télécharger les fichiers fournis

[Fichier HTML](assets/weather-offers.html)

[Fichier JavaScript](assets/weather-related-offers-script.js)


## Mettre à jour l’URL de la surface dans le fichier JavaScript

Ouvrez le `weather-related-offers-script.js` et mettez à jour le ` "web://yourdomain.com/weather/weather-offers.html#offerContainer"`en remplaçant `yourdomain.com` par le domaine réel dans lequel le fichier HTML est hébergé.

## Mise à jour de la propriété Adobe Experience Platform Tags

Ouvrez le fichier weather-offers.html dans l’éditeur de texte et remplacez la balise de script par la balise de script de votre propriété de balise Adobe Experience Platform créée à l’étape précédente de ce tutoriel. Veillez à enregistrer le fichier

```
<script src="https://assets.adobedtm.com/AEM_TAGS/launch-ENabcd1234.min.js" async></script>
```



## Fonctionnement de la page web

Une page web est créée pour tester la personnalisation contextuelle de l’offre à l’aide des données de température en temps réel. Lorsqu’un utilisateur visite la page, le navigateur demande un accès à la géolocalisation. Après approbation, la page récupère les informations météorologiques actuelles, telles que la température, la condition et la ville, via l’API OpenWeatherMap. Ces données contextuelles sont affichées pour l’utilisateur et envoyées à Adobe Experience Platform à l’aide de la SDK Web Adobe (Alloy).

L&#39;appel sendEvent est configuré avec renderDecisions : false, ce qui signifie que les offres renvoyées par Adobe Journey Optimizer sont gérées manuellement. Le script traite la réponse de prise de décision, décode le contenu et insère dynamiquement l’offre la plus pertinente dans un conteneur désigné (#offerContainer).

## Fonctionnement de JavaScript

Le JavaScript récupère dynamiquement les informations météorologiques en fonction de la localisation de l’utilisateur et utilise Adobe Experience Platform (AEP) pour diffuser des offres personnalisées. Voici une répartition des étapes :

1. **Attend le chargement de l’alliage**

   Le script s’assure que le SDK Web Adobe (Alloy) est entièrement chargé avant d’effectuer toute demande de personnalisation.

2. **Obtient l’emplacement de l’utilisateur**

   Il utilise l’API de géolocalisation du navigateur pour récupérer la latitude et la longitude actuelles de l’utilisateur.

3. **Récupère Les Données Météorologiques**

   Elle appelle l’API OpenWeatherMap pour obtenir les détails de la météo actuelle :

   Température (en °F)

   Conditions météorologiques (par exemple, « pluie », « clair »)

   Nom de la ville

   Humidité

4. **Afficher les informations météorologiques sur la page web**

   Met à jour le DOM avec un message du type :

   « La température actuelle à San Diego est de 72°F avec un ciel dégagé. »

5. **Envoie le contexte météo à AEP**

   Utilise alloy(« sendEvent ») pour envoyer des données météorologiques contextuelles à AEP

   ```javascript
   xdm: {
   eventType: "decisioning.request",
   _techmarketingdemos: {
   temperature: temp,
   weatherConditions: condition,
   cityName: city
     }
   }
   ```

6. **Récupère et effectue le rendu des offres**

   reçoit les offres renvoyées par AJO Decisioning ;

   Décode le contenu HTML.

   Injecte dynamiquement les offres dans le <div id="offerContainer"> element.

## Étapes suivantes

[Mesurez et générez des rapports sur l’impact d’AJO Decisioning.](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/reporting-on-ajo-od/introduction)

