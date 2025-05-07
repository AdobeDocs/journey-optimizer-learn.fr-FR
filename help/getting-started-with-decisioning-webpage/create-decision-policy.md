---
title: Créer Une Politique De Décision
description: Une politique de décision définit la logique utilisée pour déterminer les offres diffusées à un utilisateur ou une utilisatrice lors de la personnalisation.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17728
source-git-commit: a675979bc590190e0481e63efbc2cfd30752b7c0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 13%

---


# Créer Une Politique De Décision

Les politiques de décision sont des conteneurs pour vos offres qui tirent profit du moteur de prise de décision afin de choisir le meilleur contenu à diffuser, en fonction de l’audience.

Dans l’éditeur de personnalisation, cliquez sur l’élément Politique de décision dans le volet de navigation de gauche, puis cliquez sur Ajouter une politique de décision

![create-decision-policy](assets/decision-policy.png)

Cliquez sur Ajouter pour sélectionner la stratégie de sélection
Cliquez sur Sélectionner une offre de secours pour sélectionner l’offre de secours.
Cliquez sur Suivant pour passer en revue la politique de décision, puis sur Créer pour terminer le processus de création de la politique de décision.


![politique-décision](assets/decision-policy2.png)


## Utilisation de la politique de décision dans l’éditeur de code

Dans l’éditeur de personnalisation, cliquez sur Insérer une politique . Le code correspondant à la politique de décision est ajouté.

À ce stade, vous pouvez inclure tous les attributs de décision requis directement dans le code. Ces attributs sont définis dans le schéma utilisé par le catalogue d&#39;offres. Les attributs standard sont organisés sous l’espace de noms d’expérience __, tandis que les attributs personnalisés spécifiques à votre organisation sont stockés sous l’espace de noms d’`_<imsOrg>`.

![using_decision_policy](assets/Insert-policy.png)

Ce code parcourt une liste d’offres personnalisées choisies pour l’utilisateur et affiche le texte de chacune d’elles sur la page web. Il affiche le message (appelé offerText) de chaque offre dans un paragraphe, de sorte que les utilisateurs et utilisatrices puissent voir clairement leur contenu personnalisé.
Si aucune offre personnalisée n’est disponible, une offre de secours s’affiche pour vous assurer que l’espace n’est pas laissé vide.

Cliquez sur Enregistrer , puis sur Activer la campagne