---
title: Autorisation Capturer l’utilisateur
description: Créez une page web pour capturer le consentement de l’utilisateur pour recevoir des notifications push.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 45f86aeb8fca071436785cc55225d853bb21998f
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---

# Autorisation Capturer l’utilisateur

Cette page web capture le consentement de l’utilisateur pour recevoir des notifications push. Il invite l’utilisateur à activer les notifications à l’aide de l’API Notifications du navigateur et, une fois accepté, enregistre l’abonnement push auprès de Adobe Experience Platform à l’aide de Web SDK. Cela permet de s’assurer que seuls les utilisateurs inscrits sont éligibles à la réception de notifications push par le biais de campagnes et de parcours dans Adobe Journey Optimizer.

Pour activer les notifications push web, la page charge d’abord un fichier de configuration en appelant fetch(« /config ») dans une fonction d’initialisation. Cette configuration est diffusée par une application Node.js et inclut des valeurs de clé telles que l’identifiant du flux de données, l’identifiant de l’organisation, la clé publique VALIDE, l’identifiant de l’application et l’identifiant du jeu de données de suivi. Une fois la configuration chargée, Adobe Web SDK est initialisé et le service worker est enregistré pour prendre en charge la messagerie push. Lorsqu’un utilisateur clique sur Activer les notifications, le navigateur lui demande l’autorisation à l’aide de l’API Web Notifications. Si l’autorisation est accordée, Web SDK envoie l’abonnement push à Adobe Experience Platform et l’utilisateur est marqué comme ayant accepté l’abonnement pendant 24 heures pour éviter des invites répétées. Vous pouvez essayer ce flux sur la page web locale shop-smart.html incluse dans l’[exemple d’application](http://localhost:3000/) après le démarrage du serveur.

![request-permissions](assets/request-notifications.png)

