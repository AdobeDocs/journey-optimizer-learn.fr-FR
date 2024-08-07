---
title: Leçon 3 - Créer une campagne web in-app
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
source-git-commit: 4f5c92f79eba3651b3633b7850e993160cb1f72c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Leçon 3 - Créer une campagne web in-app

Maintenant que vous avez créé des expériences mobiles pour l’application, dans cette leçon, vous créez l’une des expériences que vous avez vues sur le site web de Fréscopa. Vous créez une campagne web in-app. Vous concevez et personnalisez un message et définissez un déclencheur qui déclenche le message.

## Objectifs d&#39;apprentissage

* Découvrez comment créer une campagne Web In-App.
* Déclenchez un message in-app.

## Exercice 3.1 Création d’une campagne web in-app

Dans cet exercice, vous créez la campagne et vous définissez la page web sur laquelle le message in-app apparaît.

1. Dans Journey Optimizer, dans le volet de navigation de gauche, sous **GESTION DES PARCOURS**, sélectionnez **Campagnes**.

1. Cliquez sur **Créer une campagne**.

   ![CreateCampaign](/help/summit/l820-lab-workbook/assets/4-1-create-campaign.png)

1. Sur la page **Créer une campagne**, dans la section **Action**, cochez la case **Message in-app** .

1. Dans la liste déroulante **Envoyer à**, sélectionnez **Web.**

1. Saisissez l’URL suivante : **https://dsn.adobe.com/web/adobe-summit-2024/exercise** - *C’est la page web sur laquelle votre message apparaîtra.*

   ![URL in-app](/help/summit/l820-lab-workbook/assets/4-1-1-in-app-url.png)

1. Cliquez sur **[!UICONTROL Créer]**.

## Exercice 3.2 - Configuration de votre campagne

Sur cette page, vous définissez les propriétés de la campagne et de l’événement qui déclenche l’affichage du message in-app dans la page web. Conservez tous les autres paramètres par défaut. Pour cet exercice, il n’est pas nécessaire de définir une audience spécifique.

### 3.2.1 [!UICONTROL Section Propriétés]

1. Dans la section **Properties** , attribuez à votre campagne un **Name** unique :

   >[!NOTE]
   > Assurez-vous de commencer le nom avec votre numéro de siège, afin que vous puissiez facilement
   > trouvez votre campagne ultérieurement.
   > 
   > Par exemple, si le numéro de votre siège est 99 : 
   >
   > ![Nom des propriétés](/help/summit/l820-lab-workbook/assets/4-1-2-properties-name.png)


### 3.2.2 Configuration de votre règle de déclenchement personnalisée

Dans cette section, vous définissez les déclencheurs du message à afficher sur le site web. Vous définissez un déclencheur unique qui vous permet d’envoyer le message à vous-même.

1. Faites défiler l&#39;écran jusqu&#39;à la **[!UICONTROL section Triggers]**, puis cliquez sur **[!UICONTROL Modifier les triggers]**.

   ![modify](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Dans le créateur de règles, cliquez sur **[!UICONTROL Application Launch]** et, dans la liste déroulante, sélectionnez *Envoi de données à Platform*.
   ![liste déroulante d’événement déclencheur](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Ajoutez une condition en cliquant sur **[!UICONTROL + Ajouter une condition]**.

   ![Bouton d’ajout de condition](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Dans la liste déroulante **[!UICONTROL Sélectionner une caractéristique]**, sélectionnez **[!UICONTROL Type d’événement XDM]**.

   ![Type d’événement XDM](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)


1. Dans le champ de texte suivant, ajoutez un *`<custom string value>`* dont vous pouvez vous souvenir, puis appuyez sur **[!UICONTROL Ajouter]** `<custom string value>` pour enregistrer la valeur.

   Cette valeur de chaîne personnalisée est utilisée ultérieurement pour déclencher votre message.

   >[!TIP]
   > L’ajout de votre numéro de siège à la valeur de chaîne personnalisée vous permet de le rendre unique et plus facile à mémoriser.
   > 
   > Par exemple : `99web`
   > 

   ![ajouter une valeur de chaîne de déclenchement personnalisée](/help/summit/l820-lab-workbook/assets/4-1-2-add-custom-trigger-dropdown.png)

1. Appuyez sur le bouton **[!UICONTROL Terminé]** en haut à droite.

>[!SUCCESS]
>
>Vous avez maintenant défini votre message in-app web avec un événement déclencheur personnalisé.
>
>![Campagne web avec déclencheur personnalisé défini](/help/summit/l820-lab-workbook/assets/4-1-2-2-web-campaign-with-custom-trigger.png)


### 3.2.3 Modification du contenu du message in-app

Dans cette section, vous définissez le contenu, la conception et la mise en page de votre message.

1. Cliquez sur le bouton **Modifier le contenu** de la section **Action** pour accéder au concept de création.

   ![Bouton Modifier le contenu](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

1. Le processus de création est le même que celui que vous avez suivi dans les exercices in-app mobiles ci-dessus. Prenez le temps de modifier librement votre message avec votre propre titre, votre corps et votre contenu multimédia.

   Si vous utilisez la disposition modale ou plein écran, vous pouvez ajouter un bouton. Vous pouvez utiliser cette URL pour ouvrir la page du produit : **https://dsn.adobe.com/web/adobe-summit-2024/P2WsaDPf_**

1. Lorsque vous avez terminé de modifier votre message, cliquez sur **[!UICONTROL Réviser pour activer]**.

1. Si tout semble correct dans l’écran de révision, cliquez sur **[!UICONTROL Activer]** pour publier votre message Web In-App.

1. Vous êtes alors redirigé vers le tableau de bord de la campagne.

   Patientez jusqu’à ce que l’état de votre campagne passe à **Live** avant de passer à 4.1.4.

## Exercice 3.3 Déclenchement du message web in-app

1. Accédez au site web de Fréscopa et accédez à la page **Exercise** sur votre navigateur.

   ![Lien des exercices web](/help/summit/l820-lab-workbook/assets/4-2-frescopa-web-exercise-link.png)

1. Veillez à actualiser la page web.

1. Saisissez la valeur de chaîne unique que vous avez définie dans votre campagne.

   ![page d’exercice](/help/summit/l820-lab-workbook/assets/4-2-exercise-page.png)

1. Cliquez sur **[!UICONTROL Envoyer]**.

>[!SUCCESS]
>
>Cliquez sur le bouton Envoyer avec votre valeur unique pour déclencher votre message Web In-App. Et votre message web in-app devrait s’afficher à l’écran.
>
>Cet exercice a simulé un événement d’envoi XDM personnalisé que vous avez vu grâce à votre expérience client Fréscopa.


## Ressources supplémentaires

**Comment visionner des vidéos :**

* [Créer une campagne in-app](/help/channels/create-an-in-app-campaign.md)
* [Créer un message in-app](/help/channels/author-in-app-messages.md)

**Documentation du produit :**

* [Prise en main du canal In-App](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Créer un message Web In-App](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app-web)
* [Concevoir votre contenu in-app](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [Vérifiez et envoyez votre notification in-app](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
