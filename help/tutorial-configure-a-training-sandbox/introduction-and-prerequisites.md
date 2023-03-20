---
title: Configurer une sandbox de formation - Introduction
description: Découvrez comment configurer une sandbox à des fins de formation. Suivez les étapes requises pour configurer les schémas, ingérer des données d’exemple et créer des événements.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: f7bfe367411f2bae23631ac4ecb34ad1d250381c
workflow-type: tm+mt
source-wordcount: '338'
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
