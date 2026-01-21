---
title: Implémenter le capping de la fréquence sur les offres Adobe Journey Optimizer (AJO) diffusées via AJO Decisioning
description: Ce tutoriel étend une implémentation Adobe Journey Optimizer (AJO) existante en activant le capping de la fréquence sur les offres diffusées à l’aide d’AJO Decisioning. Elle décrit comment capturer les événements d’impression et d’interaction utilisés dans le capping de la fréquence.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Implémenter le capping de la fréquence sur les offres Adobe Journey Optimizer (AJO) diffusées via AJO Decisioning

Ce tutoriel explique comment appliquer un capping de la fréquence aux offres dans Adobe Journey Optimizer afin de contrôler la fréquence à laquelle les utilisateurs voient la même offre au fil du temps.

En capturant les événements decisioning.propositionDisplay et decisioning.propositionInteract par le biais d’Adobe Web SDK et en les mappant à des schémas XDM dans Adobe Experience Platform (AEP), Adobe Journey Optimizer peut effectuer le suivi précis des impressions et des interactions d’offre, ce qui permet le capping de la fréquence afin de limiter la fréquence d’affichage d’une offre à un utilisateur.

## Conditions préalables pour ce tutoriel

Avant de poursuivre, assurez-vous de disposer d’une campagne Adobe Journey Optimizer valide à l’aide de Decisioning qui diffuse activement des offres vers une surface web.

Ce tutoriel suppose que la diffusion d’offres fonctionne déjà et se concentre exclusivement sur la configuration et la validation du comportement de limitation de la fréquence.


