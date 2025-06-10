---
title: Créer une formule de classement
description: Une formule de classement dans Adobe Journey Optimizer est utilisée lors de la prise de décisions sur les offres, en particulier dans le cadre d’une stratégie de sélection visant à déterminer l’ordre de priorité des offres éligibles.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: c04a15418e31dc82597b7759386907013728bb0d
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Créer une formule de classement

Une formule de classement dans Adobe Journey Optimizer est utilisée lors de la prise de décisions sur les offres, en particulier dans le cadre d’une stratégie de sélection visant à déterminer l’ordre de priorité des offres éligibles. La formule de classement entre en jeu après le filtrage de l’éligibilité, lorsque plusieurs offres remplissent les critères d’un profil donné, mais que seule la première (ou quelques-unes) doit être présentée en fonction de la logique commerciale ou du contexte du profil.

* Connexion à Journey Optimizer

* Accédez à _**Prise de décision ->Configuration de la stratégie ->Formules de classement ->Créer une formule**_

Nommez la formule _**Météo - En rapport - Offres**_



Un critère dans une formule de classement fait référence à une règle conditionnelle utilisée pour attribuer un score à une offre. Ces critères comparent les attributs de l’offre et le contexte afin de déterminer la pertinence d’une offre pour un individu spécifique.

Les 3 critères suivants sont définis pour filtrer les offres, puis attribuer un score de classement à l’offre éligible. Le critère est défini à l’aide du créateur de critères. Les données contextuelles peuvent également être utilisées pour définir les critères comme illustré dans la capture d’écran ci-dessous
![données-contextuelles](assets/context-data.png)

Les 3 critères ont tous utilisé un attribut d’offre (balise) et un attribut de données contextuelles (température) pour définir les critères.

## Critère 1

| **Balise de l’offre** | **Condition de données contextuelles** | **Logique de score** |
|------------------|---------------------|-------------------------------------|
| **chaud** | température > 80 | score=Temperature |


## Critère 2

| **Balise de météo** | **Condition de données contextuelles** | **Logique de score** |
|------------------|---------------------------|----------------------------------------------|
| **printemps** | température > 65 et &lt; 80 | score = température × 4 |

## Troisième critère

| **Balise de météo** | **Condition de données contextuelles** | **Logique de score** |
|------------------|---------------------------|----------------------------------------------|
| **froid** | température &lt; 65 | score =température |
