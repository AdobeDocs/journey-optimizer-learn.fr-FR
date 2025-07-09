---
title: Capturer les interactions d’offres avec Adobe Web SDK pour la formation des modèles d’IA
description: Cet article se concentre sur la capture de données d’interaction utilisateur, telles que les impressions d’offre et les clics, à l’aide de Adobe Experience Platform Web SDK (alloy.js). Ces données servent de base pour l’entraînement des modèles d’IA dans Adobe Journey Optimizer (AJO) afin de classer intelligemment les offres en fonction du comportement des utilisateurs et des signaux contextuels.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
source-git-commit: dfb280df3453e7811dffd95b9af664b873a9af31
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 7%

---


# Capturer les interactions d’offres avec Adobe Web SDK pour la formation des modèles d’IA

Cet article explique comment capturer des événements d’interaction d’offre (tels que des impressions ou des clics) à l’aide de Adobe Experience Platform Web SDK en appelant alloy(« sendEvent », ...) directement dans votre code JavaScript. Les données seront ingérées dans AEP et utilisées pour entraîner des modèles d’IA dans Adobe Journey Optimizer (AJO) en vue d’un classement d’offres plus intelligent basé sur le comportement en temps réel.

## Conditions préalables

Avant de commencer, assurez-vous que les éléments suivants sont en place :

- Une propriété Adobe Launch fonctionnelle avec l’extension Adobe Experience Platform Web SDK installée.

- Un [flux de données](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset) configuré et mappé à votre sandbox AEP.

- Site web sur lequel Launch est déployé.


## Créer un schéma et un jeu de données pour les événements d’interaction d’offre

Pour collecter des événements d’expérience, vous devez d’abord créer un jeu de données où ces événements seront envoyés.

Suivez les étapes mentionnées dans cet [article pour créer le schéma et le jeu de données requis](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/decisioning/experience-decisioning/collect-event-data/create-dataset)

## Création d’un flux de données dans AEP

![flux de données](assets/ai-model-data-stream.png)
Ajouter le service Adobe Experience Platform au flux de données
![data-stream-service](assets/data-stream-service.png)

## Configuration de Adobe Experience Platform Tag avec Web SDK

Dans les paramètres d’extension :

Configurer l’extension Adobe Experience Platform Web SDK pour utiliser le flux de données créé
