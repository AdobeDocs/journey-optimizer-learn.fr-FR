---
title: Personnaliser des offres web avec Decisioning
description: Découvrez comment utiliser la prise de décision Journey Optimizer (AJO) pour diffuser des offres personnalisées sur une page web en exploitant la segmentation d’audience intégrée à Experience Platform (AEP).
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
exl-id: 382ee746-e8cd-4843-bfe9-913df8914136
source-git-commit: 90f691b1cebb202ead66aafeb2e79087a8ae49ef
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 1%

---

# Utilisation de Decisioning pour personnaliser les offres web

Ce tutoriel s’appuie sur une configuration de segmentation d’audience créée précédemment à l’aide de la SDK Web Adobe Experience Platform (AEP). Dans le [tutoriel précédent](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/create-audiences-using-web-sdk/introduction), les préférences des utilisateurs, telles que l’intérêt pour les actions, les obligations ou les certificats de dépôt (CD), ont été capturées et utilisées pour segmenter les individus en audiences ciblées dans Experience Platform. Ce tutoriel s’appuie sur ces bases en utilisant Adobe Journey Optimizer (AJO) Decisioning pour diffuser des offres financières personnalisées à ces audiences en temps réel, ce qui améliore les résultats d’engagement et de conversion.

Vous pouvez tester en direct les offres AJO personnalisées via le lien ci-dessous.
[Cliquez ici pour voir la démonstration en direct](https://gbedekar489.github.io/finwise/welcome.html). La page affiche des offres en temps réel en fonction de vos préférences d’investissement.

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
