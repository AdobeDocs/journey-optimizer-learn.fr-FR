---
title: Personnaliser les offres avec des formules de classement basées sur le code postal et le revenu
description: Utilisez les formules de classement Adobe Journey Optimizer pour diffuser dynamiquement les offres financières les plus pertinentes, personnalisées en fonction du code postal et du niveau de revenu de chaque utilisateur, afin d’augmenter l’engagement et d’optimiser la personnalisation.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-27T00:00:00Z
jira: KT-18188
exl-id: 11685f7c-8048-4318-9c28-71bd7da8f7ff
source-git-commit: 85d3def3afb1d073b133df40e4cbf32d00a3a5c9
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# Personnaliser les offres avec des formules de classement basées sur le code postal de l’utilisateur et les revenus

Ce cas pratique montre comment diffuser des offres financières personnalisées en exploitant des attributs utilisateur tels que le code postal et le revenu annuel dans Adobe Journey Optimizer. En utilisant des formules de classement, les offres sont notées et hiérarchisées intelligemment en fonction de promotions spécifiques à l’emplacement et de l’éligibilité basée sur les revenus. Par exemple, les CD à haut rendement peuvent être promus auprès des utilisateurs dans les codes postaux riches, tandis que les options d&#39;investissement diversifiées sont présentées aux investisseurs émergents. Les formules de classement garantissent que chaque utilisateur reçoit des offres à la fois pertinentes et financièrement appropriées. Les critères de classement sont définis à l’aide d’attributs de profil, de signaux contextuels et de modèles d’IA facultatifs pour améliorer encore la précision des décisions. Les offres sont diffusées en temps réel par le biais de canaux web ou e-mail, ce qui entraîne un engagement et une conversion plus élevés. Cette approche associe une logique commerciale à une personnalisation pilotée par les données afin d’améliorer l’expérience utilisateur et l’impact marketing.

## Conditions préalables

Ce tutoriel s’appuie sur les concepts clés de Adobe Journey Optimizer et de Adobe Experience Platform. Avant de poursuivre, vérifiez que les conditions préalables suivantes sont remplies :

* Le [tutoriel sur l’assemblage d’identités](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorial-on-identity-stitching-in-aep/introduction) est terminé. Des identifiants CRM ont été associés avec succès aux ECID dans Adobe Experience Platform.

* Vous connaissez la création d’éléments d’offre dans AJO, notamment la définition de contenu, la configuration des métadonnées et les règles d’éligibilité.

* Vous connaissez la configuration des canaux (tels que le web ou l’e-mail) pour la diffusion d’offres.

* Vous connaissez la création et l’activation de campagnes dans AJO.

* Vous connaissez l’utilisation d’Adobe Launch (balises) pour déployer le SDK web et envoyer des événements contenant des données d’identité et de profil.

Ce tutoriel décrit les étapes suivantes d’Offer Decisioning :

* Création d’une méthode de classement à l’aide d’attributs de profil tels que le code postal et le revenu annuel.

* Définir une stratégie de sélection pour regrouper et classer les offres par priorité

* Élaboration d’une politique de décision afin de fournir l’offre la plus pertinente à chaque personne.
