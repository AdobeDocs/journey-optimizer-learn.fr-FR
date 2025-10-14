---
title: Suivre et générer des rapports sur les offres Adobe Journey Optimizer (AJO) diffusées via AJO Decisioning
description: Ce tutoriel étend une implémentation Adobe Journey Optimizer (AJO) existante qui fournit des offres personnalisées basées sur des données contextuelles telles que la température. Elle décrit comment capturer des événements d’impression et d’interaction et préparer les données pour le compte rendu des performances dans Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-07-18T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: 39376d745d851bf2c3ed3826b9f550efafd9e8f4
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Suivre et générer des rapports sur les offres Journey Optimizer diffusées via AJO Decisioning

Ce cas pratique se concentre sur l’activation des rapports et de l’analyse des performances pour les offres diffusées via Adobe Journey Optimizer (AJO). Lorsque les offres sont personnalisées et diffusées en fonction de signaux contextuels (tels que la météo ou la localisation), il est essentiel de suivre les impressions et les interactions des utilisateurs pour évaluer leur efficacité.

En capturant les événements decisioning.propositionDisplay et decisioning.propositionInteract via Adobe Web SDK et en les mappant à des schémas XDM structurés dans Adobe Experience Platform (AEP), les données d’engagement au niveau de l’offre sont disponibles pour analyse. Ces données peuvent ensuite être utilisées dans Customer Journey Analytics (CJA) pour créer des tableaux de bord, mesurer des mesures clés telles que le taux de clic publicitaire (CTR) et comparer les performances des offres sur différents segments d’audience et conditions contextuelles.

L’objectif est de fournir des informations claires et basées sur les données sur les performances des offres personnalisées et d’éclairer les futures stratégies de prise de décision.



![reporting-dashboard](assets/dashboard-reporting.png)


## Conditions préalables pour ce tutoriel

Avant de commencer, suivez le tutoriel [&#x200B; Personnaliser les offres avec les données météorologiques en temps réel .](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction) Il établit tous les composants fondamentaux, notamment :

- Intégration de Web SDK
- Configuration des offres dans Adobe Journey Optimizer (AJO)
- Prise de décision à l’aide d’attributs contextuels tels que la météo et la température
- Rendu des offres en temps réel sur une page web

Ce tutoriel s’appuie directement sur cette implémentation et se concentre spécifiquement sur la capture d’impressions et d’interactions d’offres pour le reporting et l’analyse dans Journey Optimizer.
