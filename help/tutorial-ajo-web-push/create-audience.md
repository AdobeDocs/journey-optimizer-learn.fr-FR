---
title: Créer une audience
description: Définissez un segment dans Adobe Experience Platform qui cible les utilisateurs et utilisatrices pouvant recevoir des notifications push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
exl-id: 427bb35a-d607-48be-845d-9587c4cad86b
source-git-commit: 676c21ca09e0df8d404b05081d71b147755d65d5
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---

# Créer une audience

Pour créer une audience pour la campagne, définissez un segment dans Adobe Experience Platform qui cible les utilisateurs éligibles pour recevoir des notifications push. Dans ce tutoriel, les utilisateurs disposant d’un abonnement push actif (il existe un jeton push), ne se sont pas désinscrits des notifications (l’indicateur de Place sur la liste bloquée est false) et sont associés à la configuration d’application spécifiée (l’identifiant d’application est `my-first-push`). Ces utilisateurs et utilisatrices sont entièrement éligibles pour recevoir des notifications push web par le biais de campagnes ou de parcours dans Adobe Journey Optimizer. Après la création de l’audience, assurez-vous qu’elle a été évaluée afin que les profils soient renseignés et prêts pour le ciblage.
Cette audience est ensuite utilisée dans la campagne pour diffuser des messages push web planifiés uniquement aux utilisateurs abonnés.

![create-audience](assets/push-audience.png)
