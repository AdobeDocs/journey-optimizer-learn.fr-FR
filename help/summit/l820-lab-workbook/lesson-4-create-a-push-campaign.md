---
title: Leçon 4 - Créer une campagne push
description: Passez en revue les données de profil et apprenez à créer et à envoyer aux audiences une notification push dans Journey Optimizer.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: befde57252ebc12c5d6df31fde8078e4535d1261
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 2%

---

# Leçon 4 - Créer une campagne push

Dans l’exercice précédent, vous étiez un(e) passionné(e) de café, un(e) client(e) Fréscopa. Vous avez interagi avec la marque par le biais de son site web et de l’application Fréscopa et reçu de nombreux messages transactionnels. Ces messages sont déclenchés par l’interaction de l’utilisateur avec le site web ou l’application.

Dans cet exercice, vous allez enfiler votre casquette de spécialiste marketing et mettre en œuvre une campagne marketing pour Fréscopa, qui utilisera le canal push pour cibler les utilisateurs de l’application Fréscopa. Les notifications push sont utilisées pour tenir les utilisateurs et utilisatrices de l’application informés, même lorsqu’ils ou elles n’utilisent pas l’application, mais également pour les réengager dans l’application. L&#39;objectif est d&#39;inciter le client à acheter le mélange maison, en offrant une réduction de 10%.

## Objectifs d’apprentissage

* Savoir comment créer une campagne push.
* Découvrir comment concevoir un message push.

<br>

## Exercice 4.1 - Créer une campagne push

Dans cet exercice, vous allez créer la campagne push, concevoir et personnaliser la notification push et l&#39;envoyer à votre propre appareil.

1. Dans Journey Optimizer, dans le volet de navigation de gauche, dans le **[!UICONTROL GESTION DES PARCOURS]** , sélectionnez **Campagnes**.

1. Clic **[!UICONTROL Créer une campagne]**.

   ![Créer une campagne](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Le **[!UICONTROL Créer une campagne]** , dans le  **[!UICONTROL Action]** , sélectionnez la **[!UICONTROL Notification push]** case à cocher.

1. À partir du **[!UICONTROL Surface d’application]** liste déroulante, sélectionner *[!DNL Frecopa-Push]*.

1. Clic **[!UICONTROL Créer]** pour créer une campagne push.

   ![Surface d’application](/help/summit/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Vous devriez maintenant être sur la page Propriétés de la campagne :
> ![Propriétés de la campagne](/help/summit/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Exercice 4.2 - Configurer votre campagne

Sur cette page, vous configurez les propriétés, l’audience, les actions et le planning de votre campagne.

### 4 2.1. [!UICONTROL Section Propriétés]

Donnez un nom à votre campagne. Veillez à commencer le nom par votre numéro de place afin de pouvoir facilement trouver votre campagne lorsque vous la recherchez.

Par exemple, si votre numéro de poste est 99 : `99 - 10% Discount Campaign`.

### 4 2.2.2 **[!UICONTROL Section Audience]**

1. Dans la section Audience , cliquez sur **[!UICONTROL Sélectionner une audience]**.

   ![section audience](/help/summit/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. Le **[!UICONTROL Sélectionner une audience]** écran, recherchez l’audience :

   **Lab - Seat`your seat number`**

1. Sélectionnez l’audience, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![sélection d’audience](/help/summit/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Modifier le contenu de la notification push

Dans cet exercice, vous allez concevoir et personnaliser la notification push.

1. Dans le **[!UICONTROL Action]** , cliquez sur **[!UICONTROL Modifier le contenu] bouton**.

   ![Bouton Modifier le contenu](/help/summit/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. Sur l’écran suivant, en fonction de l’appareil mobile que vous avez, sélectionnez l’une des options suivantes : [!DNL iOS™] ou [!DNL Android™] pour configurer votre contenu.

>[!BEGINTABS]

>[!TAB iOS]

![Onglet iOS](/help/summit/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Onglet Android](/help/summit/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4 2.3.1 [!UICONTROL Composer le message] section

1. **Composez votre message :** N’hésitez pas à ajouter le texte de votre choix. Voici des exemples d’utilisation :

   * Titre : `Get 10% off today!`.
   * Corps de texte : `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Composer le message](/help/summit/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Modifier le comportement en cas de clic du message en **ouvrir une page produit**

1. Dans le **[!UICONTROL Comportement en cas de clic]** , sélectionnez **[!UICONTROL Lien profond]** à partir du **[!UICONTROL Comportement en cas de clic du corps]** liste déroulante.

1. Copiez et collez l’URL suivante dans le **Champ URL**:

   `dxdemo://exoticVibes`

   ![lien profond](/help/summit/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Ajouter une image au message

1. Dans le **[!UICONTROL Ajouter un média]** , cliquez sur **[!UICONTROL Ajouter un média]**.

   ![ajouter des boutons de média](/help/summit/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. Le **[!UICONTROL Sélectionner des ressources]** dans le volet de navigation de gauche, ouvrez l’écran **Dossier Fréscopa** et sélectionnez une image dans ce dossier.

   Par exemple : `HouseBlend.png`

1. Cliquez sur l’image, puis sur le **[!UICONTROL Sélectionner] bouton** pour ajouter l’image à votre notification push.

   ![sélectionner une image](/help/summit/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. Dans l’écran d’aperçu, cliquez sur **[!UICONTROL Développer la vue]**.
   > 1. Prévisualisez votre message.
   > <br>
   >
   > ![développer la vue](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

### Exercice bonus

Si vous avez terminé cette partie de l’exercice et que vous avez encore du temps, essayez l’exercice de bonus :

+++ Exercice bonus

#### Personnalisez le message envoyé en ajoutant le prénom du destinataire

1. Clic **boîte de dialogue de personnalisation** à côté du **[!UICONTROL Corps]** champ .

   ![bouton de personnalisation](/help/summit/l820-lab-workbook/assets/2-3-personalization-button.png)

1. Le **boîte de dialogue de personnalisation** placez le curseur à l&#39;endroit où vous souhaitez ajouter le prénom dans le texte.

1. Assurez-vous que les **Attributs de profil** sont sélectionnées dans le volet de navigation de gauche.

   ![Attribut de profil](/help/summit/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. Dans le **Champ de recherche**, recherchez : `first name`.

1. Clic **+** à côté du **Prénom (Attributs de profil>Personne>Nom complet)** pour ajouter le champ de personnalisation à votre texte.

   ![Rechercher un prénom](/help/summit/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Voici à quoi votre texte doit ressembler :
   > 
   >![Jeton de personnalisation](/help/summit/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Clic **[!UICONTROL Enregistrer]** pour enregistrer la personnalisation.


   >[!SUCCESS]
   >
   > 1. Dans l’écran d’aperçu, cliquez sur **[!UICONTROL Développer la vue]**.
   > 1. Prévisualisez votre message.
   > 
   > ![développer la vue](/help/summit/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. Vérifier et activer

Si le contenu de votre message vous convient, vous pouvez activer le message :

1. Clic **[!UICONTROL Examiner pour activer]**.

   ![bouton vérifier et activer](/help/summit/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. Le **[!UICONTROL Examiner pour activer]** écran, cliquez sur **[!UICONTROL Activer]**.

   ![écran vérifier pour activer](/help/summit/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> Le **Page de présentation des campagnes**, recherchez votre campagne et vérifiez son statut.
>
> ![statut de la campagne](/help/summit/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> Le statut passe de En cours de traitement à Actif, à Terminé - cette opération peut prendre quelques minutes.
> Une fois le statut passé à terminé :
>
> ![résultats des notifications push](/help/summit/l820-lab-workbook/assets/2-3-push-notification-result.png)

## Ressources supplémentaires

**Vidéos pratiques :**

* [Configurer et envoyer une campagne de notifications push](/help/channels/create-a-push-campaign.md)

**Documentation du produit :**

* [Prise en main des notifications push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/get-started-push)
* [Créer une notification push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/create-push)
* [Créer une notification push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/design-push)
* [Vérifier et envoyer votre notification push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/send-push)
