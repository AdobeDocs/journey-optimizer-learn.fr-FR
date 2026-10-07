---
title: Activation du capping de la fréquence pour une campagne AJO
description: Le capping de la fréquence dans Adobe Journey Optimizer est appliqué au niveau de l’offre individuelle et repose sur la capture des événements d’impression et de clic de l’offre. Cela nécessite le suivi des événements decisioning.propositionDisplay et decisioning.propositionInteract à l’aide d’Adobe Web SDK et leur mappage à un schéma d’événement d’expérience XDM mis à jour dans Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
exl-id: 34027499-0037-4ea1-813b-51be15eafe24
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
source-wordcount: '230'
ht-degree: 0%
---
# Activation du capping de la fréquence pour une campagne AJO

Pour appliquer une limitation de la fréquence aux offres, procédez comme suit :

## Mise à jour du schéma d’événement

* Mettez à jour le schéma d’événement existant en ajoutant le groupe de champs comme illustré ci-dessous
* ![event-schema](assets/schema.png)

## Mettre à jour le capping de la fréquence pour l’offre


* ![offre](assets/offer-capping.png)

## Ajouter un jeton de tracking à l&#39;offre

Modifiez la politique de décision utilisée dans la campagne en ajoutant une offre de secours
![secours](assets/fallback.png)

Vous pouvez ajouter les éléments trackingToken et ItemID en cliquant sur l’icône Politique de décision dans le volet de navigation de gauche, puis en faisant défiler l’arborescence de prise de décision pour sélectionner les éléments itemID et trackingToken.

Ajoutez l’identifiant d’élément et le jeton de suivi au div contenant l’offre, comme illustré ci-dessous
![id-and-tracking-token](assets/id-and-tracking-token.png)

Cela garantit que chaque offre rendue inclut un jeton de suivi des données, essentiel pour un suivi précis des événements d’impression et de clic.


Activer la campagne modifiée.


## Envoi d’événements d’impression et de tracking

Modifiez le code JavaScript existant pour capturer et envoyer des événements d’impression et d’interaction d’offre à Adobe Experience Platform à l’aide de Adobe Web SDK. Reportez-vous à l’[exemple de code fourni ici.](capture-impression-click-events.md)
