---
title: Créer une formule de classement
description: Une formule de classement dans Adobe Journey Optimizer est utilisée lors de la prise de décisions sur les offres, en particulier dans le cadre d’une stratégie de sélection visant à déterminer l’ordre de priorité des offres éligibles.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: eee1b86e-b33f-408e-9faf-90317bc5e861
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 19%
---
# Créer une formule de classement

Une formule de classement dans Adobe Journey Optimizer est utilisée lors de la prise de décisions sur les offres, en particulier dans le cadre d’une stratégie de sélection visant à déterminer l’ordre de priorité des offres éligibles. La formule de classement entre en jeu après le filtrage de l’éligibilité, lorsque plusieurs offres remplissent les critères d’un profil donné, mais que seule la première (ou quelques-unes) doit être présentée en fonction de la logique commerciale ou du contexte du profil.

* Connexion à Journey Optimizer

* Prise de décision ->Configuration de la stratégie ->Formules de classement ->Créer une formule

Formule De Classement
![name_description](assets/formuala-ranking.png)

Un critère dans une formule de classement fait référence à une règle conditionnelle utilisée pour attribuer un score à une offre. Ces critères comparent les attributs de l’offre et le profil ou le contexte afin de déterminer la pertinence d’une offre pour un individu spécifique.



Critère 1

Cette condition filtre les éléments de décision (offres) **pour n’inclure que** les offres balisées avec « IncomeLevel ».
Ces offres filtrées passeront ensuite à l’étape suivante, telle que le classement ou la diffusion, en fonction de la logique supplémentaire que vous définissez.
![criteria_one](assets/income-related-formula.png)


L&#39;expression suivante est utilisée pour créer le score de classement

```pql
if(   offer._techmarketingdemos.offerDetails.zipCode = _techmarketingdemos.zipCode,   _techmarketingdemos.annualIncome / 1000 + 10000,   if(     not offer._techmarketingdemos.offerDetails.zipCode,     _techmarketingdemos.annualIncome / 1000,     -9999   ) )
```

Fonctionnement de la formule

* Si l’offre possède le même code postal que l’utilisateur ou l’utilisatrice, attribuez-lui un score très élevé afin qu’elle soit sélectionnée en premier.

* Si l’offre ne comporte aucun code postal (s’il s’agit d’une offre générale), attribuez-lui un score normal en fonction du revenu de l’utilisateur ou de l’utilisatrice.

* Si le code postal de l’offre est différent de celui de l’utilisateur ou de l’utilisatrice, attribuez-lui un score très faible afin qu’elle ne soit pas sélectionnée.

Ainsi, le système :

* Toujours essayer d’afficher d’abord une offre ZIP correspondante,

* Retourne à une offre générale si aucune correspondance n’est trouvée et évite d’afficher les offres destinées à d’autres codes postaux.


Si un élément d’offre ne répond à aucun des critères de filtre (comme ne pas avoir la balise « IncomeLevel »), l’offre reçoit un score de classement par défaut de 10.




