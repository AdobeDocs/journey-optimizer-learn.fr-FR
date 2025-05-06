---
title: 'Leçon 3 : créer une campagne web in-app'
description: Créez et déclenchez une campagne web in-app.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-13983
thumbnail: KT-13983.jpeg
exl-id: 0f84adfb-edb1-47fa-b696-58eec2b33bb1
source-git-commit: b5577da9a983594cb34edf5c53e2995024e30e78
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Leçon 3 : créer une campagne web in-app

Maintenant que vous avez créé des expériences mobiles pour l’application, dans cette leçon, vous allez créer l’une des expériences que vous avez vues sur le site web de Fréscopa. Vous créez une campagne web in-app. Vous concevez et personnalisez un message et définissez un déclencheur qui déclenche le message.

## Objectifs d’apprentissage

* Savoir comment créer une campagne web in-app.
* Déclenchez un message in-app.

## Exercice 3.1 : créer une campagne web in-app

Dans cet exercice, vous allez créer la campagne et définir la page web sur laquelle apparaîtra le message in-app.

1. Dans Journey Optimizer, dans le volet de navigation de gauche, sous **GESTION DES PARCOURS** sélectionnez **Campagnes**.

1. Cliquez sur **Créer une campagne**.

   ![CréerCampagne](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-create-campaign.png)

1. Sur la page **Créer une campagne**, dans la section **Action**, cochez la case **Message in-app**.

1. Dans la liste déroulante **Envoyer à**, sélectionnez **Web.**

1. Saisissez l’URL suivante : **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *Il s’agit de la page web sur laquelle votre message apparaîtra.*

   ![ URL in-app ](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. Cliquez sur **[!UICONTROL Créer]**.

## Exercice 3.2 : configurer votre campagne

Sur cette page, vous définissez les propriétés de la campagne et l’événement qui déclenche l’affichage du message in-app dans la page web. Conservez tous les autres paramètres par défaut. Pour cet exercice, vous n’avez pas besoin de définir une audience spécifique.

### 3.2.1 [!UICONTROL section Propriétés]

1. Dans la section **Propriétés**, attribuez un **Nom** unique à votre campagne :

   >[!NOTE]
   > Assurez-vous de commencer le nom par votre numéro de poste afin de pouvoir facilement
   > recherchez votre campagne ultérieurement.
   > 
   > Par exemple, si votre numéro de poste est 99 : 
   >
   > ![ Nom des propriétés ](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 Configurer votre règle de déclenchement personnalisée

Dans cette section, vous définissez les éléments qui déclenchent l’affichage du message sur le site web. Vous définissez un déclencheur unique qui vous permet d’envoyer le message uniquement à vous-même.

1. Faites défiler l’écran jusqu’à la **[!UICONTROL section Triggers]**, puis cliquez sur **[!UICONTROL Modifier les triggers]**.

   ![modifier](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Dans le créateur de règles, cliquez sur **[!UICONTROL Lancement de l’application]** et dans la liste déroulante, sélectionnez *Envoi de données à Platform*.
   ![liste déroulante d’événement trigger](/help/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Ajoutez une condition en cliquant sur **[!UICONTROL + Ajouter une condition]**.

   ![bouton ajouter une condition](/help/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Dans la liste déroulante **[!UICONTROL Sélectionner une caractéristique]**, sélectionnez **[!UICONTROL Type d’événement XDM]**.

   ![Type d’événement XDM](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. Dans le champ de texte suivant, ajoutez une *`<custom string value>`* dont vous vous souviendrez, puis appuyez sur la `<custom string value>` **[!UICONTROL Ajouter]** pour enregistrer la valeur.

   Cette valeur de chaîne personnalisée est utilisée ultérieurement pour déclencher votre message.

   >[!TIP]
   > L’ajout de votre numéro de poste à la valeur de chaîne personnalisée la rendra unique et plus facile à mémoriser.
   > 
   > Par exemple : `99web`
   > 

   ![ajouter une valeur de chaîne de déclenchement personnalisée](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. Appuyez sur le bouton **[!UICONTROL Terminé]** en haut à droite.

>[!SUCCESS]
>
>Vous avez maintenant défini votre message web in-app avec un événement déclencheur personnalisé.
>
>![Campagne web avec déclencheur personnalisé défini](/help/summit-lab-2024/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 Modifier le contenu du message in-app

Dans cette section, vous définissez le contenu, la conception et la mise en page de votre message.

1. Cliquez sur le bouton **Modifier le contenu** dans la section **Action** pour accéder à la structure de création.

   ![bouton Modifier le contenu](/help/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. Le processus de création est le même que celui que vous avez effectué dans les exercices in-app mobiles ci-dessus. Prenez le temps de modifier librement votre message avec votre propre titre, corps et contenu multimédia.

   Si vous utilisez la disposition modale ou plein écran, vous pouvez ajouter un bouton. Vous pouvez utiliser cette URL pour ouvrir la page produit : **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. Une fois la modification du message terminée, cliquez sur **[!UICONTROL Examiner pour activer]**.

1. Si tout semble correct dans l’écran de révision, cliquez sur **[!UICONTROL Activer]** pour publier votre message in-app web.

1. Vous revenez alors au tableau de bord de la campagne.

   L’unité d’attente de votre campagne passe à l’état **Actif** avant de passer à la version 4.1.4.

## Exercice 3.3 : déclencher le message in-app web

1. Rendez-vous sur le site de Fréscopa et accédez à la page **Exercice** de votre navigateur.

   ![Lien des exercices Web](/help/summit-lab-2024/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. Veillez à actualiser la page web.

1. Saisissez la valeur de chaîne unique que vous avez définie dans votre campagne.

   ![page exercice](/help/summit-lab-2024/l820-lab-workbook/assets/4-2-exercise-page.png)

1. Cliquez sur **[!UICONTROL Envoyer]**.

>[!SUCCESS]
>
>Cliquez sur le bouton Envoyer avec votre valeur unique pour déclencher votre message in-app web. De plus, votre message web in-app devrait s’afficher à l’écran.
>
>Cet exercice a simulé un événement d’envoi XDM personnalisé que vous avez vu dans votre expérience client Fréscopa.


## Ressources supplémentaires

**Vidéos pratiques :**

* [Créer une campagne in-app](/help/channels/create-an-in-app-campaign.md)
* [Créer un message in-app](/help/channels/author-in-app-messages.md)

**Documentation du produit :**

* [Prise en main du canal in-app](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Créer un message in-app web](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/in-app/create-in-app-web)
* [Concevoir votre contenu in-app](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/in-app/design-in-app)
* [Vérifier et envoyer votre notification in-app](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/in-app/send-in-app)
