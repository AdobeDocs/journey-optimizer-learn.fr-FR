---
title: Créer une formule de classement
description: Une formule de classement dans Adobe Journey Optimizer est utilisée lors de la prise de décisions sur les offres, en particulier dans le cadre d’une stratégie de sélection visant à déterminer l’ordre de priorité des offres éligibles.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
source-git-commit: 58d2964644bc199b9db212040676d87d54f767b9
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---


# Créer une formule de classement

Une formule de classement dans Adobe Journey Optimizer est utilisée lors de la prise de décisions sur les offres, en particulier dans le cadre d’une stratégie de sélection visant à déterminer l’ordre de priorité des offres éligibles. La formule de classement entre en jeu après le filtrage de l’éligibilité, lorsque plusieurs offres remplissent les critères d’un profil donné, mais que seule la première (ou quelques-unes) doit être présentée en fonction de la logique commerciale ou du contexte du profil.

* Connexion à Journey Optimizer

* Prise de décision ->Configuration de la stratégie ->Formules de classement ->Créer une formule

Formule De Classement
![name_description](assets/formuala-ranking.png)

Un critère dans une formule de classement fait référence à une règle conditionnelle utilisée pour attribuer un score à une offre. Ces critères comparent les attributs de l’offre et le profil ou le contexte afin de déterminer la pertinence d’une offre pour un individu spécifique.



Critère 1
![criteria_one](assets/criteria1.png)

Le critère 1 contient trois critères :

* offre._techmarketingdemos.offerDetails.zipCode == « 92128 » : vérifie le code postal associé à l&#39;offre.

* _techmarketingdemos.zipCode == « 92128 » : vérifie le code postal du profil de l&#39;utilisateur.

* _techmarketingdemos.annualIncome > 100000 - vérifie le niveau de revenu à partir du profil de l’utilisateur.

Si tous ces critères sont remplis, l’offre obtient un score de 40.






Critère 2
![criteria_two](assets/criteria2.png)

Le critère 2 contient trois critères :

* offre._techmarketingdemos.offerDetails.zipCode == « 92126 » : vérifie le code postal associé à l&#39;offre.

* _techmarketingdemos.zipCode == « 92126 » : vérifie le code postal du profil de l&#39;utilisateur.

* _techmarketingdemos.annualIncome &lt; 100000 - vérifie le niveau de revenu du profil de l’utilisateur.

Si tous ces critères sont remplis, l’offre obtient un score de 30.




