---
title: Configuration d’un environnement de test de formation - introduction
description: Découvrez comment configurer un environnement de test à des fins de formation. Suivez les étapes requises pour configurer les schémas, ingérer des exemples de données et créer des événements.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
exl-id: 8fa673de-9be9-4ab2-94cf-cfa8ac518223
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 9%

---

# Configuration d’un environnement de test de formation - Introduction et conditions préalables

![Tutoriel sur la bannière - Configuration d’un environnement de test de formation](./assets/ajo-banner-configure-training-sandbox.png)

Ce tutoriel est conçu pour les administrateurs et les ingénieurs de données chargés de fournir un environnement de formation Adobe Journey Optimizer. Découvrez les étapes requises pour configurer les schémas, ingérer des exemples de données et créer des événements. Vous allez également créer trois profils de test qui permettent aux apprenants de vérifier leur travail.

Les exemples de données fournis sont basés sur une société de vêtements de fiction appelée _[!DNL Luma]_. [!DNL Luma] dispose de magasins dans plusieurs pays, d’une présence en ligne sur un site web et d’applications mobiles. [!DNL Luma] utilise Adobe Journey Optimizer pour offrir des expériences connectées, contextuelles et personnalisées à ses clients.

À la fin de ce tutoriel, vous disposez d’un environnement de test qui prend en charge la variable [!DNL Luma] les cas d’utilisation couverts dans les exercices pratiques du [Défis liés à Journey Optimizer](/help/challenges/introduction-and-prerequisites.md) .

## Conditions préalables

Avant de commencer à configurer votre environnement de test de formation, vérifiez que vous disposez des éléments suivants :

1. Un développement dédié [sandbox](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/access-control/create-and-manage-sandboxes.html?lang=en).
1. [Paramètres prédéfinis de message électronique](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/channel-configuration/set-up-email-channel.html?lang=en) configurée pour le marketing et la messagerie transactionnelle.
1. **[!UICONTROL Administrateur de parcours]** et **[!UICONTROL Gestionnaire de données]** droits pour l’environnement de test de formation.
1. Votre [ID d’organisation](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=fr).

1. Les fichiers JSON contenant les exemples de données, configurés sur votre instance Journey Optimizer :

   1. Téléchargez la `luma-data.zip` fichier [here](/help/tutorial-configure-a-training-sandbox/assets/luma-data.zip), qui contient tous les fichiers JSON requis pour ce tutoriel.

   1. Dans votre dossier de téléchargements, déplacez le `luma-data.zip` vers l’emplacement souhaité sur votre ordinateur, puis décompressez-le.

      Il doit y avoir trois fichiers JSON : `luma-crm.json`, `luma-loyalty.json`, `luma-products.json`.

      Ces fichiers contiennent les exemples de données que vous ingérez dans votre environnement de test.

   1. Ouvrez chaque fichier et recherchez **`yourOrganizationID`** et remplacez-le par [ID d’organisation](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=fr).

   1. Enregistrez les fichiers.

## Commençons

Commencez par le [Configuration manuelle des données](/help/tutorial-configure-a-training-sandbox/manual-data-set-up.md). Au cours de cette étape, vous définissez la structure de données requise. Une fois la configuration de données terminée, vous pouvez ingérer des données dans votre environnement de test, puis configurer des événements.
