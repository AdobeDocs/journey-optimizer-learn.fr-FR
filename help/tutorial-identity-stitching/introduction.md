---
title: Combinaison d’identités dans AEP
description: Établissez la combinaison d’identités entre un utilisateur connu (CRMID) et un visiteur web anonyme (ECID), ce qui permet d’obtenir des profils unifiés pour la personnalisation en temps réel et Offer Decisioning dans Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 2%

---


# Description du cas d’utilisation

Dans les expériences client modernes, il est essentiel d’unifier les identités des utilisateurs sur les différents appareils et canaux. Ce cas pratique montre comment implémenter la combinaison d’identités dans Adobe Experience Platform (AEP) en liant un identifiant CRM connu, capturé lors de la connexion de l’utilisateur, à l’identifiant Experience Cloud anonyme (ECID) généré par Adobe Web SDK. En associant ces identités en temps réel, AEP peut créer un profil client plus complet couvrant à la fois le comportement anonyme et les données authentifiées. Cela permet une segmentation, une personnalisation et une prise de décision d’audience plus précises au sein d’outils tels que Adobe Journey Optimizer (AJO).

