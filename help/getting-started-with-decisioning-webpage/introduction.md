---
title: Personnaliser des offres de page web avec AJO Decisioning en fonction de l’audience
description: Découvrez comment utiliser la prise de décision Adobe Journey Optimizer (AJO) pour diffuser des offres personnalisées sur une page web en exploitant la segmentation d’audience créée dans Adobe Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
source-git-commit: 9695a4db0d0caa44a8c7d49e069320309ffc40a6
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 1%

---


# Création d’audiences AJO en fonction des préférences d’investissement des utilisateurs (actions, obligations, CD)

Ce tutoriel s’appuie sur une configuration de segmentation d’audience créée précédemment à l’aide de la SDK Web Adobe Experience Platform (AEP). Dans le tutoriel précédent, les préférences utilisateur, telles que l’intérêt pour les actions, les obligations ou les certificats de dépôt (CD), ont été capturées et utilisées pour segmenter les individus en audiences ciblées dans Adobe Experience Platform (AEP). Ce tutoriel s’appuie sur ces bases en utilisant Adobe Journey Optimizer (AJO) Decisioning pour diffuser des offres financières personnalisées à ces audiences en temps réel, ce qui améliore les résultats d’engagement et de conversion.

Vous pouvez tester en direct les offres AJO personnalisées via le lien ci-dessous.
[Cliquez ici pour voir la démonstration en direct](https://gbedekar489.github.io/finwise/welcome.html) — la page affichera les offres en temps réel en fonction de vos préférences d&#39;investissement.

## Conditions préalables pour ce tutoriel

* Accès à Adobe Experience Platform

* Compréhension de base des concepts de Adobe Experience Platform (profils, audiences, jeux de données)

* Familiarité avec Adobe Journey Optimizer

* Connaissances de base de JavaScript (lecture et écriture de fonctions simples)

* Possibilité d’utiliser les outils de développement du navigateur (onglets Console et Réseau)


## OBJECTIF

Ce tutoriel vous guide tout au long de la diffusion d’offres d’investissement personnalisées (telles que des actions, des obligations ou des CD) sur un site web à l’aide de Adobe Journey Optimizer (AJO). En exploitant la segmentation de l’audience et les stratégies de prise de décision, vous apprenez à vous assurer que chaque visiteur voit l’offre la plus pertinente en fonction de ses préférences.

## Outils utilisés

* Adobe Experience Platform (AEP)
* Adobe Journey Optimizer (AJO)
* Balises Adobe Experience Platform
* AEP Web SDK (Alloy.js)
* Segmentation d’AEP Edge
* Une page web pour afficher les offres





