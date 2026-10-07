---
title: Création de balises Adobe Experience Platform
description: Création d’audiences AJO en fonction des préférences d’investissement des utilisateurs (actions, obligations, CD)
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: 04fad076-e897-4831-9147-768721858a80
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%
---
# Création de balises Adobe Experience Platform

Les balises Adobe Experience Platform (anciennement Adobe Launch) permettent de gérer et de déployer* des technologies de marketing et d’analyse sur votre site web sans avoir à modifier le code du site.

Cette [ vidéo décrit le processus de création d’Adobe Experience Tags](https://experienceleague.adobe.com/en/playlists/experience-platform-get-started-with-tags)

* Connexion à la collecte de données
* Cliquez sur _**Tags -> Nouvelle propriété**
* Créez une balise Adobe Experience Platform appelée _**personalization-on-weather**_.
* Ajoutez les extensions suivantes à la balise .

![tags-extensions](assets/tags-extensions1.png)

* Ajoutez un élément de données appelé « ECID », comme illustré ci-dessous. Cet élément de données est utilisé ultérieurement dans les rapports

![ecid-data-element](assets/ecid-data-element.png)

* Veillez à configurer le SDK Web Adobe Experience Platform pour utiliser l’environnement approprié et le **flux de données lié à la météo** créé à l’étape précédente.

![configuration-sdk-web](assets/tags-extensions.png)



## Création et déploiement d’AEP Tags


Créez une bibliothèque et ajoutez-y toutes les ressources modifiées, comme illustré dans les captures d’écran ci-dessous.

**Ajouter une bibliothèque**

![nouvelle-bibliothèque](assets/tag-add-library.png)

**Créer une bibliothèque**

Dans l’écran Créer une bibliothèque , spécifiez le nom de la bibliothèque et l’environnement.

Ajouter toutes les ressources modifiées à cette bibliothèque
![bibliothèque-balises](assets/tag-build-library.png)

Cliquez ensuite sur le bouton Enregistrer et créer dans le développement pour créer la bibliothèque

## Inclure les balises AEP dans la page HTML

Lorsque vous publiez une propriété AEP Tags, Adobe vous fournit une balise de script que vous devez placer dans votre ` <head>` HTML ou au bas des balises ` <body>`.

1. Accédez à la propriété Balises (personnalisation selon la météo) .
2. Cliquez sur Environnements et cliquez sur l’icône d’installation de l’environnement souhaité (par exemple, Développement, Évaluation, Production).
3. Notez le code incorporé. Vous en aurez besoin à un stade ultérieur de ce tutoriel.
