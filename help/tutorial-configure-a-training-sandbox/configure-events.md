---
title: Configuration des événements
description: Configuration de trois événements requis pour les défis Journey Optimizer pratiques
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 4df1bdca81a585f728aa68519aa7ec7cd0c2f014
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 10%

---

# Configuration des événements

Dans cette section, vous configurez les trois événements requis pour les exercices pratiques dans la variable [Défis liés à Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

La vidéo suivante explique comment créer des événements :

>[!VIDEO](https://video.tv.adobe.com/v/336253?quality=12)

## Créer un événement d’achat en ligne Luma

Lors de l’utilisation de cet événement, Journey Optimizer reçoit des informations lorsqu’une personne achète des produits luma en ligne.

1. Créez un événement avec les paramètres suivants :

   | [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
   |-------------|-----------|
   | [!UICONTROL NOM] | `LumaOnlinePurchase` |
   | [!UICONTROL TYPE] | [!UICONTROL Unitaire] |
   | [!UICONTROL Type d’identifiant d’événement] | [!UICONTROL Basé sur des règles] |
   | [!UICONTROL Schéma] | `Luma Web Events Schema` |
   | [!UICONTROL Champs] | `eventType` <br>`commerce.order.priceTotal`<br>`commerce.order.purchaseOrderNumber`<br>`commerce.shipping.adress.street1`<br>`commerce.shipping.adress.city`<br>`commerce.shipping.adress.postalCode`<br>`commerce.shipping.adress.state`<br>`productListItems.quantity`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.name`<br>`productListItems.Luma Product Catalog Schema._your Organization_IDprice`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.imageURL`<br>`productListItems.Luma Product Catalog Schema._your Organization_ID.url` |

1. Ajoutez la variable [!UICONTROL Condition d’identifiant d’événement]: `LumaOnlinePurchase.eventType is commerce.purchases`:

   1. Sélectionnez l’icône représentant un crayon pour modifier le champ.

   1. Sur le **[!UICONTROL Ajout d’une condition d’identifiant d’événement]** modale, faites glisser et déposez le `eventType` sur la zone de travail.
   1. Sélectionner `commerce.purchases`.
   1. Sélectionner **[!UICONTROL Ok]** sur la zone de travail.
   1. Sélectionner **[!UICONTROL Ok]** sur le modal.

   ![Ajouter une condition d’événement](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Sélectionner [!UICONTROL ESPACE DE NOMS]: `Luma CRM ID (lumaCrmId)`

1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Créer *[!DNL Luma Wishlist Add]* event

| [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
|-------------|-----------|
| [!UICONTROL NOM] | `LumaWishlistAdd` |
| [!UICONTROL TYPE] | [!UICONTROL Unitaire] |
| [!UICONTROL Type d’identifiant d’événement] | [!UICONTROL Basé sur des règles] |
| [!UICONTROL Schéma] | `Luma Product Interactions` |
| [!UICONTROL Champs] | EventType<br>productListItem.quantity<br><b>Dans Éléments de liste de produits > Produits Luma > _*[!DNL yourOrganizationID]* > Produit :</b> <br>Nom<br>Prix<br> ProductImageURL<br>ProductURL |
| [!UICONTROL Condition] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL Espace de noms] | Email(EMail) |

## Créer *[!DNL Luma Product Restock]* event

| [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
|-------------|-----------|
| [!UICONTROL NOM] | `LumaProductRestock` |
| [!UICONTROL TYPE] | [!UICONTROL Commerciale] |
| [!UICONTROL Schéma] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Champs] | SKU <br> stockEventType<br><b> yourOrganizationID > product :</b> <br>name<br>prix<br> ImageURL<br>description |
| [!UICONTROL Condition] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType is restock |

Félicitations ! Votre environnement de test est maintenant prêt à l’emploi.
