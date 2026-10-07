---
title: Utilisation de Decisioning pour personnaliser les offres web
description: Découvrez comment utiliser la prise de décision Journey Optimizer (AJO) pour diffuser des offres personnalisées sur une page web en exploitant la segmentation d’audience intégrée à Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
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
source-wordcount: '239'
ht-degree: 7%
---
# Utilisation de Decisioning pour personnaliser les offres web

Ce tutoriel s’appuie sur une configuration de segmentation d’audience créée précédemment à l’aide de la SDK Web Adobe Experience Platform (AEP). Dans le [tutoriel précédent](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), les préférences des utilisateurs, telles que l’intérêt pour les actions, les obligations ou les certificats de dépôt (CD), ont été capturées et utilisées pour segmenter les individus en audiences ciblées dans Experience Platform. Ce tutoriel s’appuie sur ces bases en utilisant Adobe Journey Optimizer (AJO) Decisioning pour diffuser des offres financières personnalisées à ces audiences en temps réel, ce qui améliore les résultats d’engagement et de conversion.


## Conditions préalables pour ce tutoriel

* Accès à Experience Platform

* Compréhension de base des concepts Experience Platform (profils, audiences, jeux de données)

* Familiarité avec Journey Optimizer

* Connaissances de base de JavaScript (lecture et écriture de fonctions simples)

* Possibilité d’utiliser les outils de développement du navigateur (onglets Console et Réseau)


## Objectif

Ce tutoriel vous guide à travers la diffusion d’offres d’investissement personnalisées, telles que des actions, des obligations ou des CD, sur un site web à l’aide de Journey Optimizer. En utilisant la segmentation de l’audience et les stratégies de prise de décision, vous apprenez à vous assurer que chaque visiteur voit l’offre la plus pertinente en fonction de ses préférences.

## Outils utilisés

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Balises Adobe Experience Platform
* AEP Web SDK (`Alloy.js`)
* Segmentation d’AEP Edge
* Une page web pour afficher les offres
