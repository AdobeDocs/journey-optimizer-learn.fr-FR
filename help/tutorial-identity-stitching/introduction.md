---
title: Combinaison d’identités dans AEP
description: Établissez la combinaison d’identités entre un utilisateur connu (CRMID) et un visiteur web anonyme (ECID), ce qui permet d’obtenir des profils unifiés pour la personnalisation en temps réel et Offer Decisioning dans Adobe Journey Optimizer (AJO).
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
exl-id: d6a1201a-3779-4718-8ea8-b88f925f53b6
source-git-commit: 96d9d525a3d9be399f7fa229b67166acf8130721
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 1%

---

# Description du cas d’utilisation

Dans les expériences client modernes, il est essentiel d’unifier les identités des utilisateurs sur les différents appareils et canaux. Ce cas pratique montre comment implémenter la combinaison d’identités dans Adobe Experience Platform (AEP) en liant un identifiant CRM connu, capturé lors de la connexion de l’utilisateur, à l’identifiant Experience Cloud anonyme (ECID) généré par Adobe Web SDK. En associant ces identités en temps réel, AEP peut créer un profil client plus complet couvrant à la fois le comportement anonyme et les données authentifiées. Cela permet une segmentation, une personnalisation et une prise de décision d’audience plus précises au sein d’outils tels que Adobe Journey Optimizer (AJO).

## 🧠 requises pour le tutoriel sur l’assemblage d’identités

Pour tirer le meilleur parti de ce tutoriel, il est recommandé de connaître les éléments suivants :

- **Concepts De Base De Adobe Experience Platform (AEP)**\
  Présentation des schémas, des jeux de données, des identités, des politiques de fusion et des profils en temps réel.

- **Modélisation des schémas et des identités**\
  Possibilité de configurer des champs d’identité dans des schémas basés sur un profil et un événement.

- **Adobe Launch (balises) et Web SDK (Alloy.js)**\
  Expérience de la configuration d’éléments de données et de règles pour envoyer des données à AEP à l’aide de Web SDK.

- **Concepts de base de JavaScript**\
  Familiarisez-vous avec les fonctions de capture des entrées utilisateur, de déclenchement d’événements et d’appels d’API de débogage.

- **Outils de débogage AEP**\
  Possibilité d’utiliser le débogueur AEP et la visionneuse de graphiques d’identités pour valider la combinaison d’identités.

- **Ingestion de données dans AEP**\
  Des compétences pour charger des données d’exemple dans des jeux de données et assurer la qualité des données.


