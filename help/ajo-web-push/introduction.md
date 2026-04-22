---
title: Notification push web dans AJO
description: Ce tutoriel explique comment implémenter des notifications push web à l’aide de Adobe Journey Optimizer (AJO). Vous apprendrez comment capturer l’accord préalable des utilisateurs et utilisatrices avec le Web SDK, envoyer des notifications par le biais de campagnes planifiées et déclencher des messages push en temps réel à l’aide d’un événement price.drop personnalisé avec AEP Tags.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Notification push web dans Adobe Journey Optimizer

Les notifications push web sont un moyen puissant de réengager les utilisateurs en temps réel. Ce tutoriel vous guide tout au long de leur implémentation à l’aide de Adobe Journey Optimizer (AJO). Commencez par utiliser le SDK web pour capturer les préférences de souscription des utilisateurs pour les notifications push, afin d’assurer une expérience d’abonnement transparente et conforme. Ensuite, vous allez créer une campagne pour envoyer des notifications push aux utilisateurs qui se sont inscrits, ce qui permettra l’engagement basé sur l’audience. Enfin, vous apprendrez à tirer parti des balises AEP pour déclencher un événement de baisse de prix personnalisé, qui lance un parcours dans AJO et diffuse en temps opportun des notifications push personnalisées en fonction du comportement de l&#39;utilisateur en temps réel.

Exemple de page web pour permettre aux utilisateurs de s’inscrire aux notifications

![activer-notifications](assets/enable-notifications.png)

Exemple de page web pour déclencher l’événement de chute des prix

![déclencher une chute des prix](assets/trigger-price-drop-event.png)

## Conditions préalables

Ce tutoriel est conçu pour être pratique et facile à suivre. Bien qu’aucune expertise approfondie ne soit requise, une connaissance de base des concepts suivants sera utile :

- Adobe Journey Optimizer (création de parcours ou de campagnes)
- Collecte de données AEP (balises) et SDK Web
- Concepts de base de Adobe Experience Platform tels que les schémas et les événements
- Quelques concepts de développement web généraux et JavaScript
- Connaissances de base de Node.js (pour générer des clés VAPID et servir un point d’entrée de configuration simple)

Si vous découvrez l’un de ces domaines, ne vous inquiétez pas : le tutoriel vous guidera tout au long des étapes clés.
Ce tutoriel se concentre sur l’implémentation d’un cas d’utilisation complet des notifications push web. Une connaissance pratique des outils et des concepts ci-dessus vous aidera donc à suivre efficacement.


## 🔔 Activer les notifications du navigateur

Si les notifications sont bloquées ou n’apparaissent pas, vous devrez peut-être les activer dans les paramètres de votre navigateur. Consultez les guides ci-dessous :

- **Google Chrome (Windows/macOS)**\
  <https://support.google.com/chrome/answer/3220216>

- **Microsoft Edge (Windows)**\
  <https://support.microsoft.com/en-us/microsoft-edge/manage-website-notifications-in-microsoft-edge>

- **Safari (macOS)**\
  <https://support.apple.com/guide/safari/customize-website-notifications-sfri40734/mac>

- **Safari (iPhone/iPad)**\
  <https://support.apple.com/en-us/HT213893>


## Exemple d’application


Pour vous aider à suivre, un exemple complet d’application est disponible.

- [Démonstration en direct - Opt-in :](https://ajo-web-push.onrender.com/)

- [Déclencher un événement de chute de prix:](https://ajo-web-push.onrender.com/price-drop-trigger.html)

- [Code Source :](https://github.com/gbedekar489/ajo-web-push)

Vous pouvez explorer la démonstration en direct pour voir le flux en action ou cloner le référentiel pour exécuter le projet localement.

