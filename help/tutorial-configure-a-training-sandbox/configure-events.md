---
title: Configurer des événements
description: Configurer trois événements requis pour les défis pratiques Journey Optimizer
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
jira: KT-9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: df055830da42b94d751890af6c19074ddfea2237
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 97%

---

# Configurer des événements

Dans cette section, vous configurez les trois événements requis pour les exercices pratiques dans les [Défis Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

La vidéo suivante vous explique comment créer des événements :

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12&learn=on)

## Créer un événement d’achat en ligne Luma

Lors de l’utilisation de cet événement, Journey Optimizer reçoit des informations lorsqu’une personne achète des produits Luma en ligne.

1. Créez un événement avec les paramètres suivants :

   | [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
   |-------------|-----------|
   | [!UICONTROL NOM] | `LumaOnlinePurchase` |
   | [!UICONTROL TYPE] | [!UICONTROL Unitaire] |
   | [!UICONTROL Type d’identifiant d’événement] | [!UICONTROL Basé sur des règles] |
   | [!UICONTROL Schéma] | `Luma Web Events Schema` |
   | [!UICONTROL Champs] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. Ajoutez la [!UICONTROL condition d’identifiant d’événement] : `LumaOnlinePurchase.eventType is commerce.purchases` :

   1. Sélectionnez l’icône représentant un crayon pour modifier le champ.

   1. Sur la fenêtre modale **[!UICONTROL Ajouter une condition d’identifiant d’événement]**, faites glisser et déposez le `eventType` sur la zone de travail.
   1. Sélectionnez `commerce.purchases`.
   1. Sélectionnez **[!UICONTROL OK]** dans la zone de travail.
   1. Sélectionnez **[!UICONTROL OK]** dans la boîte de dialogue modale.

   ![Ajout d’une condition d’événement.](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Sélectionnez l’[!UICONTROL ESPACE DE NOMS] : `Luma CRM ID (lumaCrmId)`.

1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Créer un événement *[!DNL Luma Product Restock]*

| [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
|-------------|-----------|
| [!UICONTROL NOM] | `LumaProductRestock` |
| [!UICONTROL TYPE] | [!UICONTROL Entreprise] |
| [!UICONTROL Schéma] | [!DNL Luma Product Inventory Event Schema] |
| [!UICONTROL Champs] | SKU <br> stockEventType<br><b>LumaProductCatalogSchema_yourOrganizationID.product :</b> <br>Nom<br> Prix<br> ImageURL<br> Description |
| [!UICONTROL Condition] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType est en réapprovisionnement |

Félicitations ! Vous pouvez désormais utiliser votre sandbox.
