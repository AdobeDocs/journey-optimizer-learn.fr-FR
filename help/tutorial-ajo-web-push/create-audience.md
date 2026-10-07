---
title: Créer une audience
description: Définissez un segment dans Adobe Experience Platform qui cible les utilisateurs et utilisatrices pouvant recevoir des notifications push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%
---
# Créer une audience

Pour créer une audience pour la campagne, définissez un segment dans Adobe Experience Platform qui cible les utilisateurs éligibles pour recevoir des notifications push. Dans ce tutoriel, les utilisateurs disposant d’un abonnement push actif (il existe un jeton push), ne se sont pas désinscrits des notifications (l’indicateur de Place sur la liste bloquée est false) et sont associés à la configuration d’application spécifiée (l’identifiant d’application est `my-first-push`). Ces utilisateurs et utilisatrices sont entièrement éligibles pour recevoir des notifications push web par le biais de campagnes ou de parcours dans Adobe Journey Optimizer. Après la création de l’audience, assurez-vous qu’elle a été évaluée afin que les profils soient renseignés et prêts pour le ciblage.
Cette audience est ensuite utilisée dans la campagne pour diffuser des messages push web planifiés uniquement aux utilisateurs abonnés.

![create-audience](assets/push-audience.png)
