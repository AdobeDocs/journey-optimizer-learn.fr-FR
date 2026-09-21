---
source-git-commit: fc279f2ff41f624e4a6a0c4c930cedfcc2745dc5
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 3%
---
# Activités en direct

## Qu&#39;est-ce que c&#39;est ?

Les **activités en direct** vous permettent de diffuser des mises à jour persistantes en temps réel, qui informent les clients de la progression d’une activité (préparation d’une commande, livraison en transit ou déplacement). Au lieu d’envoyer une nouvelle notification pour chaque mise à jour, une seule activité active est créée, puis mise à jour et se termine au fur et à mesure de l’évolution de l’activité, en synchronisant l’écran de verrouillage ou l’ombrage de notification du client avec ce qui se passe.

Adobe Journey Optimizer prend en charge les activités en direct sur les deux principales plateformes mobiles :

* **[Activités iOS Live](/help/channels/ios-live-activities.md)** : mises à jour riches en temps réel sur l’écran de verrouillage d’iPhone et l’île dynamique.
* **[Mises à jour Android Live Updates](/help/channels/android-live-updates.md)** : mises à jour persistantes en temps réel dans l’ombre de notification Android.

Pour configurer Mobile SDK et utiliser les API pour démarrer, mettre à jour et terminer les expériences en direct sur vos parcours clients, voir [Configurer l’activité en direct](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/live-activity/configure-live-activity/mobile-live-configuration-sdk){target="_blank"}.

## Cas d’utilisation

Choisissez les activités en direct comme canal préféré lorsque vous devez :

| # | Avantage | Pourquoi | Exemples de cas d’utilisation |
|---|---------|-----|-------------------|
| 1 | Aperçu des progrès en cours | Les mises à jour apparaissent directement sur l’écran de verrouillage ou sur l’icône dynamique ou l’ombre de notification, sans que l’utilisateur ouvre l’application | <ul><li>Tracking des diffusions alimentaires</li><li>Ride-hailing status</li><li>Scores sportifs en direct</li></ul> |
| 2 | Réduire la lassitude des notifications | Une seule activité est mise à jour sur place au lieu de déclencher des notifications push répétées | <ul><li>Étapes de préparation et de livraison de la commande</li><li>Mises à jour de l’embarquement et des barrières</li></ul> |
| 3 | Contexte de courte durée et critique | Idéal pour les activités dont le début et la fin sont clairs | <ul><li>Compteurs à rebours côté trottoir</li><li>Sessions d’entraînement ou de minutage</li></ul> |
| 4 | Interface utilisateur native et lisible | Utilise des surfaces natives du système d’exploitation (île dynamique, écran de verrouillage, ombre de notification) pour une expérience à haute visibilité et à faible frottement | <ul><li>Tracking des packages</li><li>Mises à jour de la file d’attente ou du temps d’attente</li></ul> |

## Si *non* utiliser des activités en direct

* Pour les états de longue durée ou ouverts sans fin claire, mettez fin à l’activité une fois le processus sous-jacent terminé.
* Pour le contenu promotionnel ou marketing : utilisez plutôt des notifications push, des messages in-app ou des cartes de contenu.
* Lorsque la cadence de mise à jour est très élevée, les mises à jour fréquentes peuvent être ralenties par le système d’exploitation ou être bruyantes pour l’utilisateur ou l’utilisatrice.
* Si votre application ne prend pas en charge les versions minimales de système d’exploitation requises pour les activités iOS Live ou les mises à jour Android Live.
