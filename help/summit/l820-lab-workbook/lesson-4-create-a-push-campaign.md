---
title: Leçon 4 - Création d’une campagne push
description: Passez en revue les données de profil et apprenez à créer et à envoyer aux audiences une notification push dans Journey Optimizer.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
source-git-commit: c590b47ad3dfc54badbac0d8fcaff6b9dd053cc1
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---


# Leçon 4 - Création d’une campagne push

Dans l&#39;exercice précédent, vous étiez un passionné de café, un client de Fréscopa. Vous avez interagi avec la marque via son site web et l&#39;application Fréscopa et avez reçu de nombreux messages transactionnels. Ces messages sont déclenchés par l’interaction de l’utilisateur avec le site web ou l’application.

Au cours de cet exercice, vous allez mettre votre marketeur en service et mettre en oeuvre une campagne marketing pour Fréscopa, qui utilisera le canal push pour cibler les utilisateurs de l’application Fréscopa. Les notifications push sont utilisées pour informer les utilisateurs de l’application, même s’ils n’utilisent pas l’application, mais également pour les réengager dans l’application. L&#39;objectif est d&#39;inciter le client à acheter le mélange, en offrant une remise de 10%.

## Objectifs d’apprentissage

* Découvrez comment créer une campagne push.
* Découvrez comment concevoir un message push.

<br>

## Exercice 4.1 - Création d’une campagne push

Dans cet exercice, vous créez la campagne push, concevez et personnalisez la notification push, puis envoyez la notification push à votre propre appareil.

1. Dans Journey Optimizer, dans le volet de navigation de gauche, dans la **[!UICONTROL GESTION DES PARCOURS]** , sélectionnez **Campagnes**.

1. Cliquez sur **[!UICONTROL Créer une campagne]**.

   ![Créer une campagne](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Sur le **[!UICONTROL Créer une campagne]** , dans la variable  **[!UICONTROL Action]** , sélectionnez **[!UICONTROL Notification push]** .

1. Dans la **[!UICONTROL Surface de l’application]** menu déroulant, sélectionnez *[!DNL Frecopa-Push]*.

1. Cliquez sur **[!UICONTROL Créer]** pour créer une campagne push.

   ![Surface de l’application](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Vous devez maintenant vous trouver sur la page des propriétés de Campaign :
> ![Propriétés de la campagne](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Exercice 4.2 - Configuration de votre campagne

Sur cette page, vous pouvez configurer les propriétés, l’audience, les actions et le planning de votre campagne.

### 4.2.1 [!UICONTROL Section Propriétés]

Attribuez un nom à votre campagne. Veillez à commencer le nom par votre numéro de siège, de sorte que vous puissiez facilement trouver votre campagne lorsque vous la cherchez.

Par exemple, si le numéro de votre siège est 99 : `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL Section Audience]**

1. Dans la section Audience, cliquez sur **[!UICONTROL Sélection de l’audience]**.

   ![section d&#39;audience](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. Sur le **[!UICONTROL Sélection de l’audience]** écran, recherchez l’audience :

   **Lab - Seat`your seat number`**

1. Sélectionnez l’audience, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![sélection d’audiences](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Modification du contenu de la notification push

Dans cet exercice, vous concevez et personnalisez la notification push.

1. Dans le **[!UICONTROL Action]** , cliquez sur le bouton **[!UICONTROL Modifier le contenu] button**.

   ![Bouton Modifier le contenu](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. Dans l’écran suivant, en fonction du périphérique mobile dont vous disposez, sélectionnez l’une des options suivantes : [!DNL iOS™] ou [!DNL Android™] pour configurer votre contenu.

>[!BEGINTABS]

>[!TAB iOS]

![Onglet iOS](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Onglet Android](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 [!UICONTROL Composer le message] section

1. **Composez votre message :** N’hésitez pas à ajouter le texte de votre choix. Voici des exemples que vous pouvez utiliser :

   * Titre : `Get 10% off today!`.
   * Corps de texte : `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Composer le message](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Modifier le comportement en cas de clic du message en **ouvrir une page de produit ;**

1. Dans le **[!UICONTROL Comportement en cas de clic]** , sélectionnez **[!UICONTROL Deeplink]** de la **[!UICONTROL Comportement de clic sur le corps]** menu déroulant.

1. Copiez et collez l’URL suivante dans le **Champ URL**:

   `dxdemo://exoticVibes`

   ![lien profond](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Ajout d’une image au message

1. Dans le **[!UICONTROL Ajouter un média]** , cliquez sur **[!UICONTROL Ajouter un média]**.

   ![ajouter des boutons multimédias](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. Sur le **[!UICONTROL Sélectionner les ressources]** dans le volet de navigation de gauche, ouvrez la **Dossier Fréscopa** et sélectionnez une image dans ce dossier.

   Par exemple : `HouseBlend.png`

1. Cliquez sur l’image, puis sur le bouton **[!UICONTROL Sélectionner] button** pour ajouter l’image à votre notification push.

   ![sélectionner une image](/help/summit/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. Dans l’écran de prévisualisation, cliquez sur **[!UICONTROL Développer la vue]**.
   > 1. Prévisualisez votre message.
   > <br>
   >
   > ![développer la vue](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

### Exercice bonus

Si vous avez terminé cette partie de l’exercice et que vous avez encore du temps, essayez l’exercice supplémentaire :

+++ Exercice bonus

#### Personnaliser le message que vous envoyez en ajoutant le prénom du destinataire

1. Cliquez sur **boîte de dialogue de personnalisation** en regard de **[!UICONTROL Corps]** champ .

   ![bouton de personnalisation](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. Sur le **boîte de dialogue de personnalisation** , placez le curseur à l’endroit où vous souhaitez ajouter le prénom dans le texte.

1. Assurez-vous que la variable **Attributs de profil** sont sélectionnés dans le volet de navigation de gauche.

   ![Attribut de profil](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. Dans le **Champ de recherche**, recherchez : `first name`.

1. Cliquez sur **+** en regard de **Prénom (Attributs de profil > Personne > Nom complet)** pour ajouter le champ de personnalisation à votre texte.

   ![Recherche du prénom](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Voici à quoi votre texte doit ressembler :
   > 
   >![Jeton de personnalisation](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** pour enregistrer la personnalisation.


   >[!SUCCESS]
   >
   > 1. Dans l’écran de prévisualisation, cliquez sur **[!UICONTROL Développer la vue]**.
   > 1. Prévisualisez votre message.
   > 
   > ![développer la vue](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4 Vérifier et activer

Si le contenu de votre message vous satisfait, vous pouvez activer le message :

1. Cliquez sur **[!UICONTROL Réviser pour activer]**.

   ![bouton de révision et d’activation](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. Sur le **[!UICONTROL Réviser pour activer]** écran, cliquez sur **[!UICONTROL Activer]**.

   ![révision pour activer l’écran](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> Sur le **Page d’aperçu des campagnes**, recherchez votre campagne et vérifiez son état.
>
> ![état de la campagne](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> L’état passe du traitement à l’état actif, à l’état terminé. Cela peut prendre quelques minutes.
> Une fois que l’état a été remplacé par Terminé :
>
> ![résultats push](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)


**Merci !**

Merci pour votre participation. Veuillez nous faire part de vos commentaires, sur la façon dont nous l&#39;avons fait et si le laboratoire a répondu à vos attentes, en répondant au questionnaire Lab 820 Session dans l&#39;application Summit.

