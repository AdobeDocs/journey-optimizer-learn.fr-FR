---
title: Activation du capping de la fréquence pour une campagne AJO
description: Le capping de la fréquence dans Adobe Journey Optimizer est appliqué au niveau de l’offre individuelle et repose sur la capture des événements d’impression et de clic de l’offre. Cela nécessite le suivi des événements decisioning.propositionDisplay et decisioning.propositionInteract à l’aide d’Adobe Web SDK et leur mappage à un schéma d’événement d’expérience XDM mis à jour dans Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-18526
source-git-commit: bef6d831c639d40514552dae3ff20132626a4a09
workflow-type: tm+mt
source-wordcount: '224'
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


