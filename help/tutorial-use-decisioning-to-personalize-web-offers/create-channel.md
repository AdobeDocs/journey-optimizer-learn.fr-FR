---
title: Créer Un Canal D’Expérience Basé Sur Le Code
description: Une configuration de canal dans AJO définit la manière dont le contenu personnalisé, tel que les offres, est diffusé par un canal spécifique comme le web, les e-mails, les applications mobiles ou d’autres points de contact numériques.
role: User
feature: Decisioning
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: a7247b19-877b-4f62-b4d1-1c3a762b3433
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
source-wordcount: '97'
ht-degree: 0%
---
# Créer un canal d’expérience basé sur du code

Une expérience basée sur le code dans Adobe Journey Optimizer (AJO) [!UICONTROL Decisioning] est une configuration qui permet la diffusion d’offres personnalisées directement dans une page web à l’aide de JavaScript côté client. Au lieu de s’appuyer sur des modèles prédéfinis ou des outils de mise en page visuelle, cette approche permet aux développeurs et aux développeuses de contrôler entièrement quand et où les offres sont rendues à l’aide d’Adobe Web SDK (`Alloy.js`).

![create-channel](assets/cbe-channel.png)
