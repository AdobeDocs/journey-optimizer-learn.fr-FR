---
title: Personnalisation des offres avec des données météorologiques en temps réel dans Adobe Journey Optimizer à l’aide de Web SDK
description: Ce tutoriel vous explique comment diffuser des offres dynamiques et adaptées à la météo dans Adobe Journey Optimizer à l’aide de données contextuelles en temps réel et de l’API Adobe Web SDK Personalization. Vous apprendrez à transmettre des attributs météorologiques (tels que la température et les conditions) de votre site web à Adobe Experience Platform, à les mapper à votre schéma d’événement et à les utiliser dans les règles de décision et les formules de classement afin de personnaliser les offres au moment du chargement de la page. Idéal pour les professionnels du marketing et les développeurs qui cherchent à améliorer les expériences digitales avec un contexte environnemental en temps réel.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---

# Description du cas d’utilisation

L’utilisation de données météorologiques dans Adobe Journey Optimizer (AJO) pour diffuser des offres permet aux entreprises de personnaliser les expériences client en fonction des conditions environnementales en temps réel. La météo est un puissant signal contextuel. Les besoins et les comportements des gens changent selon la météo. En utilisant les données météorologiques :

Proposer des offres adaptées à l’humeur et à l’environnement des clients

Par une journée chaude, montrez une offre de boisson froide ou de climatiseurs. Par temps de pluie, promouvez des vestes ou des parapluies

Exemple d&#39;offre basée sur la météo


![offres-météo](assets/offers-use-case.png)



## Conditions préalables pour ce tutoriel

* Accès à Experience Platform

* Compréhension de base des balises Adobe Experience Platform

* Compréhension de base des concepts Experience Platform (profils, audiences, jeux de données)

* Familiarité avec Journey Optimizer

* Connaissances de base de JavaScript (lecture et écriture de fonctions simples)

* Possibilité d’utiliser les outils de développement du navigateur (onglets Console et Réseau)
