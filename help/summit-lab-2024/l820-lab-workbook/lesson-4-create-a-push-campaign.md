---
title: 'Leçon 4 : créer une campagne push'
description: Passez en revue les données de profil et apprenez à créer et à envoyer aux audiences une notification push dans Journey Optimizer.
feature: Push
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14980
exl-id: 0f82d6a5-18c0-45f2-968e-a678fc2d5768
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 2%

---

# Leçon 4 : créer une campagne push

Dans l’exercice précédent, vous étiez un(e) passionné(e) de café, un(e) client(e) Fréscopa. Vous avez interagi avec la marque par le biais de son site web et de l’application Fréscopa et reçu de nombreux messages transactionnels. Ces messages sont déclenchés par l’interaction de l’utilisateur avec le site web ou l’application.

Dans cet exercice, vous allez enfiler votre casquette de spécialiste marketing et mettre en œuvre une campagne marketing pour Fréscopa, qui utilisera le canal push pour cibler les utilisateurs de l’application Fréscopa. Les notifications push sont utilisées pour tenir les utilisateurs et utilisatrices de l’application informés, même lorsqu’ils ou elles n’utilisent pas l’application, mais également pour les réengager dans l’application. L&#39;objectif est d&#39;inciter le client à acheter le mélange maison, en offrant une réduction de 10%.

## Objectifs d’apprentissage

* Savoir comment créer une campagne push.
* comprendre comment concevoir un message push ;

<br>

## Exercice 4.1 - Créer une campagne push

Dans cet exercice, vous allez créer la campagne push, concevoir et personnaliser la notification push et l&#39;envoyer à votre propre appareil.

1. Dans Journey Optimizer, dans le volet de navigation de gauche, dans la section **[!UICONTROL GESTION DES PARCOURS]**, sélectionnez **Campagnes**.

1. Cliquez sur **[!UICONTROL Créer une campagne]**.

   ![Créer une campagne](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Sur la page **[!UICONTROL Créer une campagne]**, dans la section **[!UICONTROL Action]**, cochez la case **[!UICONTROL Notification push]**.

1. Dans le menu déroulant **[!UICONTROL Surface d’application]**, sélectionnez *[!DNL Frecopa-Push]*.

1. Cliquez sur **[!UICONTROL Créer]** pour créer une campagne push.

   ![Surface d’application](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-app-surface.png)

>[!SUCCESS]
>
>Vous devriez maintenant être sur la page Propriétés de la campagne :
> ![Propriétés de la campagne](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-2-campaign-properties.png)

## Exercice 4.2 - Configurer votre campagne

Sur cette page, vous configurez les propriétés, l’audience, les actions et le planning de votre campagne.

### 4.2.1 [!UICONTROL section Propriétés]

Donnez un nom à votre campagne. Veillez à commencer le nom par votre numéro de poste afin de pouvoir facilement trouver votre campagne lorsque vous la recherchez.

Par exemple, si votre numéro de poste est 99 : `99 - 10% Discount Campaign`.

### 4.2.2 **[!UICONTROL Section Audience]**

1. Dans la section Audience , cliquez sur **[!UICONTROL Sélectionner une audience]**.

   ![section audience](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-2-5-audience-section.png)

1. Sur l’écran **[!UICONTROL Sélectionner une audience]**, recherchez l’audience :

   **Lab - Seat`your seat number`**

1. Sélectionnez l’audience, puis cliquez sur **[!UICONTROL Enregistrer]**.

   ![sélection d’audiences](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-2-7-select-audience.png)

### 4.2.3 Modifier le contenu de la notification push

Dans cet exercice, vous allez concevoir et personnaliser la notification push.

1. Dans la section **[!UICONTROL Action]**, cliquez sur le bouton **[!UICONTROL Modifier le contenu]**.

   ![bouton Modifier le contenu](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-action-edit-content-button.png)

1. Sur l’écran suivant, en fonction de l’appareil mobile que vous avez, sélectionnez l’onglet [!DNL iOS™] ou [!DNL Android™] pour configurer votre contenu.

>[!BEGINTABS]

>[!TAB iOS]

![Onglet iOS](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-ios-tab.png)

>[!TAB Android]

![Onglet Android](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-android-tab.png)

>[!ENDTABS]

#### 4.2.3.1 section [!UICONTROL &#x200B; Composer le message &#x200B;]

1. **Composez votre message :** n’hésitez pas à ajouter le texte de votre choix. Voici des exemples d’utilisation :

   * Titre : `Get 10% off today!`
   * Corps de texte : `Today only! Get 10% off on your House Blend coffee purchase!`

     ![Composer le message](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-compose-message.png)

#### 4.2.3.2 Modifier le comportement en cas de clic du message pour **ouvrir une page produit**

1. Dans la section **[!UICONTROL Comportement en cas de clic]**, sélectionnez **[!UICONTROL Lien profond]** dans le menu déroulant **[!UICONTROL Comportement en cas de clic]**.

1. Copiez et collez l’URL suivante dans le champ **URL** :

   `dxdemo://exoticVibes`

   ![lien profond](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-deeplink.png)

#### 4.2.3.3 Ajouter une image au message

1. Dans la section **[!UICONTROL Ajouter un média]**, cliquez sur **[!UICONTROL Ajouter un média]**.

   ![ajout de boutons de média](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-add-media-buttons.png)

1. Sur l’écran **[!UICONTROL Sélectionner Assets]**, dans le volet de navigation de gauche, ouvrez le dossier **Fréscopa** et sélectionnez une image de ce dossier.

   Par exemple : `HouseBlend.png`

1. Cliquez sur l’image, puis sur le bouton **[!UICONTROL Sélectionner]** pour ajouter l’image à votre notification push.

   ![sélectionner une image](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-3-select-image.png)

   >[!SUCCESS]
   >
   > 1. Dans l’écran de prévisualisation, cliquez sur **[!UICONTROL Développer la vue]**.
   > 1. Prévisualisez votre message.
   > <br>
   >
   > ![développer la vue](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

### Exercice bonus

Si vous avez terminé cette partie de l’exercice et que vous avez encore du temps, essayez l’exercice de bonus :

+++ Exercice bonus

#### Personnalisez le message que vous envoyez en ajoutant le prénom du destinataire

1. Cliquez sur **boîte de dialogue de personnalisation** en regard du champ **[!UICONTROL Corps]**.

   ![bouton de personnalisation](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-button.png)

1. Sur l’écran **boîte de dialogue de personnalisation**, placez le curseur à l’endroit où vous souhaitez ajouter le prénom dans le texte.

1. Assurez-vous que les **attributs de profil** sont sélectionnés dans le volet de navigation de gauche.

   ![Attribut de profil](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-body-profile-attributes.png)

1. Dans le **champ de recherche**, recherchez : `first name`.

1. Cliquez sur **+** en regard du **Prénom (Attributs de profil>Personne>Nom complet)** pour ajouter le champ de personnalisation à votre texte.

   ![Rechercher le prénom](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalize-search-first-name.png)

   >[!SUCCESS]
   >
   > Voici à quoi votre texte doit ressembler :
   > 
   >![Jeton Personalization](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-personalization-token.png)

1. Cliquez sur **[!UICONTROL Enregistrer]** pour enregistrer la personnalisation.


   >[!SUCCESS]
   >
   > 1. Dans l’écran de prévisualisation, cliquez sur **[!UICONTROL Développer la vue]**.
   > 1. Prévisualisez votre message.
   > 
   > ![développer la vue](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-3-expand-view.png)

+++

### 4.2.4. Vérifier et activer

Si le contenu de votre message vous convient, vous pouvez activer le message :

1. Cliquez sur **[!UICONTROL Vérifier pour activer]**.

   ![bouton vérifier et activer](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-and-activate-button.png)

1. Sur l’écran **[!UICONTROL Vérifier pour activer]**, cliquez sur **[!UICONTROL Activer]**.

   ![vérifier pour activer l’écran](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-4-review-to-activate.png)

>[!SUCCESS]
> Sur la page **Aperçu des campagnes**, recherchez votre campagne et vérifiez son statut.
>
> ![statut de la campagne](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-push-completed.png)
> 
> Le statut passe de En cours de traitement à Actif, à Terminé - cela peut prendre quelques minutes.
> Une fois le statut modifié en terminé :
>
> ![résultats push](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-push-notification-result.png)

## Ressources supplémentaires

**Vidéos pratiques :**

* [Configurer et envoyer une campagne de notifications push](/help/channels/create-a-push-campaign.md)

**Documentation du produit :**

* [Prise en main des notifications push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/get-started-push)
* [Créer une notification push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/create-push)
* [Créer une notification push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/design-push)
* [Vérifier et envoyer votre notification push](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/push/send-push)
