---
title: Créer un flux de données
description: Cette page vous guide tout au long de la création d’un flux de données dans Adobe Experience Platform, qui est nécessaire pour collecter des données à partir de Web SDK et les acheminer vers AEP et Adobe Journey Optimizer. Le flux de données agit comme une connexion entre votre application web et les services Adobe, permettant le traitement des données d’événement et d’abonnement push.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Créer un flux de données

Un flux de données dans Adobe Experience Platform (AEP) agit comme point d’entrée qui reçoit les données envoyées à partir du SDK Web. Il achemine ces données vers des services configurés tels qu’AEP, Adobe Analytics ou Adobe Journey Optimizer. Dans ce tutoriel, le flux de données est utilisé pour envoyer des données d’abonnement push web et des événements price.drop à AEP en vue de leur activation.

## Création d&#39;un schéma d&#39;événement pour le suivi des notifications push

Créez un schéma XDM ExperienceEvent nommé `SchemaForPushNotification`. Ajoutez les groupes de champs `Push Notification Tracking` et `Commerce Details` à ce schéma. Les champs du groupe de champs Détails du Commerce seront utilisés pour capturer des informations sur le produit et déclencher l’événement price.drop personnalisé.

![event-schema](assets/event-schema.png)

## Créer un schéma de profil pour enregistrer le consentement de l’utilisateur

Pour ce tutoriel, nous utilisons le `AJO Push Profile Schema` prêt à l’emploi. Ce schéma stocke les détails de l&#39;abonnement push de l&#39;utilisateur, y compris le jeton push requis pour diffuser les notifications push web.

![profile_schema](assets/profile-schema.png)

## Créer des jeux de données pour le schéma

Créez un jeu de données nommé `DataSetForPushNotification` à l’aide du schéma d’événement créé précédemment. Pour les données de profil, utilisez le `AJO Push Profile Dataset` prêt à l’emploi, qui est associé au schéma de profil push. Notez l’ID de `DataSetForPushNotification`, car il sera requis ultérieurement dans le tutoriel lors de la configuration de l’application via le fichier .env.

## Créer un flux de données à l’aide du jeu de données d’événement et de profil

Créez un flux de données nommé WebPushDataStream à l’aide des jeux de données d’événement et de profil créés à l’étape précédente. Notez l’identifiant du flux de données, car il sera requis ultérieurement dans le tutoriel lors de la configuration de l’application via le fichier .env.

![flux de données](assets/datastream.png)
