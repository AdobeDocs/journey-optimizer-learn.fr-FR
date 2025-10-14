---
title: Déclenchement du Parcours Adobe Journey Optimizer à l’aide d’Adobe Web SDK
description: Découvrez comment démarrer un parcours Adobe Journey Optimizer à partir d’événements de site tels que les connexions des utilisateurs et utilisatrices en utilisant l’AEP Web SDK configuré via les balises Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-09-24T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-19287
source-git-commit: 6927cade07790603e711f4e6e4c3f6982a56e6f5
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# Déclenchement du Parcours Adobe Journey Optimizer à l’aide d’Adobe Web SDK

Dans cette extension du tutoriel Combinaison d’identités, le parcours Adobe Journey Optimizer est déclenché pour envoyer un e-mail à l’utilisateur connecté à l’aide de son profil assemblé. **Cet article suppose que vous connaissez le canal e-mail et que vous êtes familiarisé avec la création de contenu pour ce canal.**

## Créer une configuration de canal e-mail

* Se connecter à _**Journey Optimizer**_
* Accédez à _**Administration -> Canaux -> Créer une configuration de canal**_
* Sélectionnez **E-mail** dans la liste des canaux. Fournissez un nom et une description significatifs.
* Renseignez les paramètres d’e-mail.
* Fournissez les détails d’exécution, comme illustré ci-dessous. L’e-mail est envoyé à l’adresse électronique du profil stockée dans le champ
* ![canal e-mail](assets/email-channel-execution.png)
* Activation de la configuration du canal e-mail

## Créer un événement

* Se connecter à _**Journey Optimizer**_
* Accédez à _**Administration -> Configurations**_
* Cliquez sur le bouton Gérer de la carte Événements et cliquez sur Créer un événement. Spécifiez les valeurs comme illustré ci-dessous
* ![parcours-event](assets/journey-event1.png)

* Vérifiez que eventType de l’événement est égal à LoginEvent. Le type de `LoginEvent` est défini dans la balise Adobe Experience Platform.
* Enregistrer l’événement

## Créer un parcours

* Se connecter à _**Journey Optimizer**_
* Accédez à _**Gestion des Parcours -> Parcours -> Créer un Parcours**_
* Faites glisser et déposez l’événement _**UserLoggedIn**_ sur la zone de travail
* Glissez-déposez E-mail à partir du menu d’actions. Configurez l’action e-mail pour utiliser la configuration du canal e-mail créée précédemment.
* Publiez le parcours.

## Déclenchement du parcours

Le parcours est déclenché lorsque la payload de l&#39;événement envoyée via le SDK Web correspond à ce qui est configuré dans le parcours. Dans cet exemple, l’événement est `UserLoggedIn` type d’événement est `LoginEvent`.

* Vérifiez-le en consultant le rapport de parcours
* ![parcours-rapport](assets/journey-triggered-report.png)




