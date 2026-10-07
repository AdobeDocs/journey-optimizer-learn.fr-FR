---
title: Implémenter le capping de la fréquence sur les offres Adobe Journey Optimizer (AJO) diffusées via AJO Decisioning
description: Ce tutoriel étend une implémentation Adobe Journey Optimizer (AJO) existante en activant le capping de la fréquence sur les offres diffusées à l’aide d’AJO Decisioning. Elle décrit comment capturer les événements d’impression et d’interaction utilisés dans le capping de la fréquence.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: ae74485f-9ea1-428d-9c07-5db0c5cf93fb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%
---
# Implémenter le capping de la fréquence sur les offres Adobe Journey Optimizer (AJO) diffusées via AJO Decisioning

Ce tutoriel explique comment appliquer un capping de la fréquence aux offres dans Adobe Journey Optimizer afin de contrôler la fréquence à laquelle les utilisateurs voient la même offre au fil du temps.

Ce tutoriel suppose que vous avez déjà configuré une campagne AJO en suivant le tutoriel [personnalisation des offres en fonction des conditions météorologiques](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/introduction)

En capturant les événements decisioning.propositionDisplay et decisioning.propositionInteract par le biais d’Adobe Web SDK et en les mappant à des schémas XDM dans Adobe Experience Platform (AEP), Adobe Journey Optimizer peut effectuer le suivi précis des impressions et des interactions d’offre, ce qui permet le capping de la fréquence afin de limiter la fréquence d’affichage d’une offre à un utilisateur.

## Conditions préalables pour ce tutoriel

Avant de poursuivre, assurez-vous de disposer d’une campagne Adobe Journey Optimizer valide à l’aide de Decisioning qui diffuse activement des offres vers une surface web.

Ce tutoriel suppose que la diffusion d’offres fonctionne déjà et se concentre exclusivement sur la configuration et la validation du comportement de limitation de la fréquence.




