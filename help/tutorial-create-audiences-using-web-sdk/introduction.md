---
title: Créer des audiences à l’aide de Web SDK
description: Dans ce tutoriel, vous apprendrez à capturer les préférences utilisateur par le biais d’un formulaire web, à envoyer ces données à Adobe Experience Platform (AEP) en temps réel et à qualifier les utilisateurs de manière dynamique en audiences ciblées en fonction de leurs sélections. En associant Adobe Tags (Launch), AEP Web SDK (Alloy.js) et la segmentation Edge, vous offrez des opportunités de personnalisation immédiates aux clients intéressés par les actions, les obligations ou les certificats de dépôt (CD).
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
exl-id: ebaa3aa5-0a08-43fd-8d06-8e4b5d8dee05
source-git-commit: 163edfb3367d03729d68c9339ee2af4a0fe3a1b3
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Créer des audiences à l’aide de Web SDK

Dans ce tutoriel, vous apprendrez à capturer les préférences utilisateur par le biais d’un formulaire web, à envoyer ces données à Adobe Experience Platform (AEP) en temps réel et à qualifier les utilisateurs de manière dynamique en audiences ciblées en fonction de leurs sélections. En associant Adobe Tags (Launch), AEP Web SDK (Alloy.js) et la segmentation Edge, vous offrez des opportunités de personnalisation immédiates aux clients intéressés par les actions, les obligations ou les certificats de dépôt (CD).

## Conditions préalables pour ce tutoriel

* Accès à Adobe Experience Platform

* Compréhension de base des concepts de Adobe Experience Platform (profils, audiences, jeux de données)

* Familiarité avec les balises Adobe (Launch) — configuration des éléments de données et des règles

* Connaissances de base de JavaScript (lecture et écriture de fonctions simples)

* Possibilité d’utiliser les outils de développement du navigateur (onglets Console et Réseau)


## OBJECTIF

L’objectif de ce tutoriel est de créer et de qualifier trois audiences distinctes dans Adobe Experience Platform (AEP) :

* Clients intéressés par les actions

* Clients intéressés par les obligations

* Clients intéressés par les CD

Les utilisateurs envoient leurs préférences par le biais d’un formulaire web, qui sont ensuite ingérées via AEP Web SDK à l’aide d’Adobe Launch, ce qui permet de qualifier les audiences en temps réel.

## Outils utilisés

* Adobe Experience Platform (AEP)

* Balises Adobe Experience Platform

* AEP Web SDK (Alloy.js)

* Segmentation d’AEP Edge

* Une page web avec un formulaire de préférence
