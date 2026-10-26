---
title: Configurer une sandbox de formation - Introduction
description: Découvrez comment configurer une sandbox à des fins de formation. Apprenez à configurer les schémas, ingérer des données d’exemple et créer des événements en suivant les étapes ci-après.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00.000Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
    internal-label: Data management activity
  - id: d556b755-390a-43f0-be32-a08cf6236126
    internal-label: Configuration
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
    internal-label: Administration
subfeature_v2:
  - id: d2e8a157-b3b0-4143-9ff3-809bf400be56
    internal-label: Sandboxes
  - id: efb19423-4da4-4fd1-88d8-5ee8c71ae766
    internal-label: Application settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: ht
source-wordcount: '353'
ht-degree: 100%
---
# Configurer une sandbox de formation - Introduction et conditions préalables

![Tutoriel sur la bannière - Configuration d’une sandbox de formation.](./assets/ajo-banner-configure-training-sandbox.png)

Ce tutoriel est conçu pour l’administration et les ingénieures et ingénieurs de données en charge de fournir un environnement de formation Adobe [!DNL Journey Optimizer]. Découvrez les étapes requises pour configurer les schémas, ingérer des données d’exemple et créer des événements. Vous créez également trois profils de test qui permettent aux personnes apprenantes de vérifier leur travail.

Les données d’exemple fournies sont basées sur une entreprise de vêtements de sport fictive appelée _[!DNL Luma]_. [!DNL Luma] dispose de magasins dans plusieurs pays, d’une présence en ligne sur un site web et d’applications mobiles. [!DNL Luma] utilise Adobe Journey Optimizer pour offrir des expériences connectées, contextuelles et personnalisées à sa clientèle.

À la fin de ce tutoriel, vous disposez d’une sandbox qui prend en charge les cas d’utilisation [!DNL Luma] couverts dans les exercices pratiques de la section [Défis Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

## Conditions préalables

Avant de commencer à configurer votre sandbox de formation, vérifiez que vous disposez des éléments suivants :

1. Une [sandbox](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=fr) de développement dédiée.

1. Des [paramètres prédéfinis d’e-mail](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/set-up-email-channel.html?lang=fr) configurés pour les messages marketing et transactionnels.

1. Les droits d’**[!UICONTROL Administration Journey]** et de **[!UICONTROL Gestionnaire de données]** pour la sandbox de formation.

1. Votre [ID d’organisation](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=fr).

1. Les fichiers JSON contenant les données d’exemple, configurés sur votre instance Journey Optimizer :

   1. Téléchargez le fichier `luma-sample-data.zip` [ici](/help/tutorial-configure-a-training-sandbox/assets/luma-data/luma-sample-data.zip), qui contient tous les fichiers JSON requis pour ce tutoriel.

   1. Dans votre dossier de téléchargements, déplacez le fichier `luma-data.zip` vers l’emplacement souhaité sur votre ordinateur, puis décompressez-le.

      Ces fichiers contiennent les données d’exemple pour votre sandbox de formation.

   1. Ouvrez chaque fichier et recherchez **`yourOrganizationID`**, puis remplacez-le par votre [ID d’organisation](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=fr).

   1. Enregistrez les fichiers.

## Nous pouvons démarrer.

Commencez par la [configuration manuelle des données](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md).

Au cours de cette étape, vous définissez la structure de données requise. Une fois la configuration des données terminée, vous pouvez ingérer les données dans votre sandbox, puis configurer des événements.
