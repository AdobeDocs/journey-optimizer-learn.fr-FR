---
title: Créer un canal push
description: La configuration du canal push définit le mode de diffusion des notifications push web, y compris les paramètres de l'application et les détails spécifiques à la plateforme. Elle associe également votre configuration push aux informations d’identification requises, telles que les clés VALID, ce qui permet à AJO d’envoyer des notifications aux utilisateurs abonnés.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Créer un canal push

La première étape consiste à créer un canal push dans Adobe Journey Optimizer. Dans le cadre de cette configuration, vous devez générer des clés VAPID, qui sont requises pour authentifier et activer les notifications push web. Ces clés sont ensuite utilisées dans la configuration du canal push, ce qui permet à AJO d&#39;envoyer en toute sécurité des notifications aux utilisateurs abonnés.

## Générer des clés valides

VAPID (Voluntary Application Server Identification) est une norme push web qui permet à votre serveur de s&#39;identifier auprès des services push (tels que Chrome, Edge, etc.) à l&#39;aide de paires de clés publiques/privées, de sorte que le fournisseur push sache qui envoie la notification.

Il est généré à l’aide d’un outil comme web-push generate-valid-keys, qui crée une clé publique (partagée avec le navigateur) et une clé privée (conservée sur votre serveur) utilisées conjointement pour authentifier et envoyer en toute sécurité les messages push.

Pour ce tutoriel, nous avons utilisé Node.js pour générer les clés VALID.

Vérifiez que Node.js est installé. Exécutez ensuite la commande suivante :
```npm install web-push -g ```

![web-push](assets/install-web-push.png)

```web-push generate-vapid-keys```

![valide](assets/vapid-keys.png)

## Créer des informations d’identification des notifications push

* Connexion à Journey Optimizer

* Accédez à Administration | Canaux | PARAMÈTRES PUSH | Informations d’identification push | Créer des informations d’identification push

* ![informations d’identification push](assets/push-credential.png)

## Créer une configuration de canal

* Connexion à Journey Optimizer

* Accédez à Administration | Canaux | Créer une configuration de canal
  ![configuration-canal](assets/push-channel.png)
