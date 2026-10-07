---
title: Combinaison d’identités dans AEP
description: Mettez en place un regroupement d’identités entre l’utilisateur connu ou l’utilisatrice connue (CRMID) et un visiteur ou une visiteuse web anonyme (ECID), afin de créer un profil unifié pour la personnalisation en temps réel et la prise de décisions sur les offres dans Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 11%
---
# Combinaison d’identités dans AEP

Dans les expériences client modernes, il est essentiel d’unifier les identités des utilisateurs sur les différents appareils et canaux. Ce cas pratique montre comment implémenter la combinaison d’identités dans Adobe Experience Platform (AEP) en liant un identifiant CRM connu, capturé lors de la connexion de l’utilisateur, à l’Experience Cloud ID anonyme (ECID) généré par Adobe Web SDK. En associant ces identités en temps réel, AEP peut créer un profil client plus complet couvrant à la fois le comportement anonyme et les données authentifiées. Cela permet une segmentation, une personnalisation et une prise de décision d’audience plus précises au sein d’outils tels que Adobe Journey Optimizer (AJO).

## Compétences requises pour le tutoriel sur la combinaison d’identités

Pour tirer le meilleur parti de ce tutoriel, il est recommandé de connaître les éléments suivants :

- **Concepts De Base De Adobe Experience Platform (AEP)**\
  Présentation des schémas, des jeux de données, des identités, des politiques de fusion et des profils en temps réel.

- **Modélisation des schémas et des identités**\
  Possibilité de configurer des champs d’identité dans des schémas basés sur un profil et un événement.

- **Adobe Launch (balises) et Web SDK (Alloy.js)**\
  Expérience de la configuration d’éléments de données et de règles pour envoyer des données à AEP à l’aide de Web SDK.

- **Concepts de base de**\
  Familiarisez-vous avec les fonctions de capture des entrées utilisateur, de déclenchement d’événements et d’appels d’API de débogage.

- **Outils de débogage**\
  Possibilité d’utiliser le débogueur AEP et la visionneuse de graphiques d’identités pour valider la combinaison d’identités.

- **Ingestion de données dans AEP**\
  Des compétences pour charger des données d’exemple dans des jeux de données et assurer la qualité des données.


