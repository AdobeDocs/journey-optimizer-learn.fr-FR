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
source-git-commit: a9fc14da78e1c67b01aef5dcdd417ce02d36d50a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Tester la solution

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

   reçoit les offres renvoyées par AJO ;

   Décode le contenu HTML.

   Injecte dynamiquement les offres dans le <div id="offerContainer"> element.

7. **Exemple d’Assets**

   La page web utilisée pour tester la solution peut être téléchargée

[Page web](assets/weather-offers.html)

[Code JavaScript](assets/weather-related-offers-script.js)

