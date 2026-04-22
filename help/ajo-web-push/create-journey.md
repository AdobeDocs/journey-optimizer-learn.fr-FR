---
title: Créer un parcours
description: Créer un parcours déclenché sur l’événement price.drop
feature: Push
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-04-21T00:00:00Z
jira: KT-20879
source-git-commit: 3d342c5c4de4dda221ce4427b1e4aef7ef8c22cc
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Créer un Parcours

Au cours de cette étape, vous allez créer un parcours dans Adobe Journey Optimizer qui est déclenché par l’événement price.drop personnalisé. Lorsque cet événement est reçu, le parcours démarre en temps réel et envoie une notification push aux utilisateurs qui se sont inscrits, ce qui permet un engagement piloté par l&#39;événement.

Pour créer un parcours déclenché sur l’événement price.drop, procédez comme suit

* Connexion à Journey Optimizer
* Accédez à Gestion des Parcours | Parcours | Créer un Parcours

![create-parcours &#x200B;](assets/create-journey.png)

## Ajouter PriceDropEvent

Faites glisser le `PriceDropEvent` de la section Événements vers la zone de travail
![price-drop-event](assets/add-price-drop-event.png)

## Ajouter une action Push

Développez la section Actions . Faites glisser et déposez l’activité `Action` sur la zone de travail et sélectionnez Push comme type d’action
![push-action](assets/add-push-action.png)

## Configuration de l’action Push

Sélectionnez l’activité Notification push et cliquez sur Configurer l’action .

![configure-push-action](assets/configure-push-action.png)

## Configuration du canal des notifications push

Associez `MyFirstWebPushChannel` configuration créée précédemment dans le tutoriel à cette notification push.

![configuration-canal](assets/journey-actions.png)

## Composer un message de notification push

Ajoutez une combinaison de contenu statique et dynamique à la notification push à l’aide de l’éditeur de personnalisation pour rendre le message plus attrayant et plus pertinent.

Pour commencer à composer le message, cliquez sur `Content` pour ouvrir l’onglet Contenu , où vous pouvez définir le texte fixe et les champs dynamiques dérivés des données d’événement.
![content-push](assets/compose-message.png)

Indiquez le titre du message push, puis ouvrez l’éditeur de personnalisation pour composer le corps du message. Le contenu inclut dynamiquement les noms du ou des produits dont les prix ont chuté. Pour ce faire, utilisez la fonction each [helper](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/content-management/personalization/functions/helpers#each)
pour effectuer une itération sur la liste des produits et effectuer le rendu de leurs noms dans le message.

## Composer le corps du message

Sélectionnez et insérez la fonction `Each` à partir du menu des fonctions d’assistance .
![fonction d’assistance](assets/journey-content-helper-function.png)

Sélectionnez les attributs contextuels | Journey Orchestration | Événements | PriceDropEvent | productListItems | Name

Cliquez sur l’icône « + » pour insérer le tableau dans chaque boucle de l’éditeur de personnalisation. Ensuite, mettez à jour le contenu du message pour qu’il corresponde au format affiché dans la capture d’écran de référence. Notez que l’identifiant d’événement affiché dans votre environnement peut différer de celui affiché.

![attributs-contextuels](assets/journey-content-context-attributes.png)

Enfin, enregistrez toutes vos modifications et publiez le parcours. Une fois publié, le parcours devient actif et écoute les événements price.drop entrants. Chaque fois qu’un événement de ce type est reçu, le parcours est déclenché en temps réel et une notification push est envoyée aux utilisateurs et utilisatrices qui se sont inscrits pour recevoir des notifications, ce qui permet un engagement opportun et pertinent.

## Tester la solution

Pour déclencher l’événement price.drop, ouvrez la page [déclencheur de chute des prix](http://localhost:3000/price-drop-trigger.html) sélectionnez un ou plusieurs produits, puis cliquez sur Déclencher la chute des prix. L’événement est alors envoyé à travers la couche de données Adobe à l’aide des balises AEP, qui initie ensuite le parcours et diffuse la notification push en temps réel.



