---
title: Créer une campagne
description: Créez une campagne pour cibler les utilisateurs et utilisatrices qui se sont inscrits pour recevoir des notifications push et envoyer le message à l’heure planifiée.
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00.000Z
jira: KT-20879
exl-id: 94fda23f-e26a-494b-8e5c-6c442bae61c4
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: 66e1fd99-672d-5d64-aa58-eca107f0fbae
    internal-label: Push
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 2%
---
# Créer une campagne

Au cours de cette étape, vous allez créer une campagne dans Adobe Journey Optimizer pour envoyer des notifications push web planifiées aux utilisateurs qui se sont inscrits. La campagne cible une audience éligible et diffuse des messages à un moment prédéfini, ce qui permet un engagement planifié et basé sur l’audience.

* Connexion à Journey Optimizer
* Accédez à Gestion des Parcours | Campagnes | Créer des campagnes

## Spécifier les paramètres de la campagne

Spécifier le nom de la campagne

![nom-campagne](assets/campign-push-notification.png)

## Associer l’action à la campagne

Associez la configuration de canal push créée précédemment dans ce tutoriel

![campaign-action](assets/campign-push-notification-action.png)

## Associer une audience à la campagne

Associer le `AudienceForPush` d’audience à la campagne

![campaign-audience](assets/campign-push-notification-audience.png)

## Créer du contenu pour la notification push

Créez du contenu push de base pour tester la notification push. Indiquez le titre et le corps du message comme illustré ci-dessous

![contenu-pour-notification push](assets/campign-push-notification-content.png)

## Planifier la campagne

Planifier la campagne en fonction de vos besoins

![schedule-campaign](assets/campign-push-notification-schedule.png)

Enfin, assurez-vous d’activer la campagne.

## Tester la campagne

Pour tester la campagne, activez d’abord les notifications sur la page web [en vous inscrivant](http://localhost:3000) lorsque vous y êtes invité. Une fois la souscription effectuée, attendez que la campagne s’exécute à l’heure planifiée. Lorsque la campagne s’exécute, vous devriez recevoir la notification push dans votre navigateur.
