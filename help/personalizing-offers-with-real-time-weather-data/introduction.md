---
title: Personnalisation des offres avec des données météorologiques en temps réel dans Adobe Journey Optimizer à l’aide du SDK web
description: Ce tutoriel démontre comment proposer des offres dynamiques adaptées à la météo dans Adobe Journey Optimizer, à l’aide de données contextuelles en temps réel et de l’API de personnalisation du SDK web d’Adobe. Vous apprendrez à transmettre des attributs météorologiques (tels que la température et les conditions) de votre site web à Adobe Experience Platform, à les mapper à votre schéma d’événement et à les utiliser dans les règles de décision et les formules de classement afin de personnaliser les offres au moment du chargement de la page. Idéal pour les personnes spécialisées dans le marketing et membres des équipes de développement qui souhaitent enrichir les expériences numériques grâce à un contexte environnemental en temps réel.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10
jira: KT-18258
exl-id: f40dd541-470c-4f42-8181-eb1c277ebaa3
source-git-commit: b4cf9b677c6bc142e1013649db16b3a70b405052
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 43%
---
# Description du cas d’utilisation

L’utilisation de données météorologiques dans Adobe Journey Optimizer (AJO) pour diffuser des offres permet aux entreprises de personnaliser les expériences client en fonction des conditions environnementales en temps réel. La météo est un puissant signal contextuel. Les besoins et les comportements des gens changent selon la météo. En utilisant les données météorologiques :

Proposer des offres adaptées à l’humeur et à l’environnement des clients

Par une journée chaude, montrez une offre de boisson froide ou de climatiseurs. Par temps de pluie, promouvoir des vestes ou des parapluies

Exemple d&#39;offre basée sur la météo


![offres-météo](assets/offers-use-case.png)



## Conditions préalables pour ce tutoriel

* Accès à Experience Platform.

* Compréhension de base des balises Adobe Experience Platform.

* Compréhension de base des concepts Experience Platform (profils, audiences, jeux de données).

* Connaissance de Journey Optimizer.

* Connaissances de base de JavaScript (lecture et écriture de fonctions simples).

* Possibilité d’utiliser les outils de développement du navigateur (onglets Console et Réseau).
