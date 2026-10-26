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
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: aeebb91a-f216-4d5f-8da1-3a7e6f696ed0
    internal-label: Data management activity
  - id: d556b755-390a-43f0-be32-a08cf6236126
    internal-label: Configuration
  - id: bb359667-ec7d-4d4b-8663-5850fc219d32
    internal-label: Administration
subfeature_v2:
  - id: d2e8a157-b3b0-4143-9ff3-809bf400be56
    internal-label: Sandboxes
  - id: efb19423-4da4-4fd1-88d8-5ee8c71ae766
    internal-label: Application settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: ht
source-wordcount: '158'
ht-degree: 100%
---
# Configurer des événements

Dans cette section, vous configurez les trois événements requis pour les exercices pratiques dans les [Défis Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

La vidéo suivante vous explique comment créer des événements :

>[!VIDEO](https://video.tv.adobe.com/v/3431514?captions=fre_fr&quality=12&learn=on){transcript=true}

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
| [!UICONTROL Champs] | SKU <br> stockEventType<br><b>LumaProductCatalogSchema._yourOrganizationID.product : </b> <br>Nom<br> Prix<br> ImageURL<br> Description |
| [!UICONTROL Condition] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType est en réapprovisionnement |

Félicitations ! Vous pouvez désormais utiliser votre sandbox.
