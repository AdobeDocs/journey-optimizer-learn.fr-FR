---
title: Configuration des événements
description: Configuration de trois événements requis pour répondre aux défis de Journey Optimizer
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
recommendations: noDisplay, noCatalog
exl-id: c7826818-c28a-493b-8aba-9d8a8102336d
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 9%

---

# Configuration des événements

Dans cette section, vous configurez les trois événements requis pour les exercices pratiques dans la variable [Défis liés à Journey Optimizer](/help/challenges/introduction-and-prerequisites.md).

Regarder la vidéo [Créer des événements](/help/set-up-journeys/create-events.md) pour savoir comment créer des événements.

## Créer un événement d’achat Luma Online

1. Dans le volet de navigation de gauche, accédez à [!UICONTROL ADMINISTRATION] et sélectionnez *[!UICONTROL Configuration]*
1. Dans la [!UICONTROL Tableau de bord], sélectionnez *[!UICONTROL Gérer*]* Événements

![Gestion des événements](assets/create-events.png)

1. Cliquez sur *[!UICONTROL Créer un événement]*
1. Renseignez les détails et les paramètres de l’événement :

   | [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
   |-------------|-----------|
   | [!UICONTROL NOM] | `LumaOnlinePurchase` |
   | [!UICONTROL TYPE] | [!UICONTROL Unitaire] |
   | [!UICONTROL Type d’identifiant d’événement] | [!UICONTROL Basé sur des règles] |
   | [!UICONTROL Schéma] | Interactions produit Luma |
   | [!UICONTROL Champs] | EventType <br>Order.priceTotal<br>purchaseOrderNumber<br>productListItems.quantity<br><b>Dans Éléments de liste de produits > Produits Luma > _*[!DNL yourOrganizationID]* > Produit :</b> <br> Nom<br>Prix<br>ProductImageURL<br>ProductURL |

1. Ajoutez la variable [!UICONTROL Condition d’identifiant d’événement]: **[!DNL LumaOnlinePurchase.eventType is commerce.purchases]**

   1. Sélectionner l’icône représentant un crayon pour modifier le champ
   2. Sur le [!UICONTROL Ajout d’une condition d’identifiant d’événement] modale, faites glisser et déposez le `eventType` sur la zone de travail
   3. Sélectionner `commerce.purchases`
   4. Sélectionnez ok sur la zone de travail.
   5. Sélectionnez ok sur le modal.

![Ajouter une condition d’événement](/help/tutorial-configure-a-training-sandbox/assets/Event-lumaOnlinePurchase-condition-1.png)

1. Sélectionner [!UICONTROL ESPACE DE NOMS]: `Email(Email)`

1. Sélectionnez **[!UICONTROL Enregistrer]**.

## Créer *[!DNL Luma Wishlist Add]* Événement

| [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
|-------------|-----------|
| [!UICONTROL NOM] | `LumaWishlistAdd` |
| [!UICONTROL TYPE] | [!UICONTROL Unitaire] |
| [!UICONTROL Type d’identifiant d’événement] | [!UICONTROL Basé sur des règles] |
| [!UICONTROL Schéma] | `Luma Product Interactions` |
| [!UICONTROL Champs] | EventType<br>productListItem.quantity<br><b>Dans Éléments de liste de produits > Produits Luma > _*[!DNL yourOrganizationID]* > Produit :</b> <br>Nom<br>Prix<br> ProductImageURL<br>ProductURL |
| [!UICONTROL Condition] | [!DNL LumaWishlistAdd.eventType is commerce.saveForLaters] |
| [!UICONTROL Espace de noms] | Email(EMail) |

## Créer *[!DNL Luma Product Restock] Événement

| [!UICONTROL Paramètre] | [!UICONTROL Valeur] |
|-------------|-----------|
| [!UICONTROL NOM] | `LumaProductRestock` |
| [!UICONTROL TYPE] | [!UICONTROL Commerciale] |
| [!UICONTROL Schéma] | [!DNL Luma Product Inventory Events] |
| [!UICONTROL Champs] | productID <br> stockEventType<br><b>Dans Produit > Produits Luma > *[!DNL yourOrganizationID]* > Produit :</b> <br>Nom<br>Prix<br> ProductImageURL<br>Description |
| [!UICONTROL Condition] | LumaProductRestock._`your organization's ID`.inventoryEvent.stockEventType is restock |

## Félicitations

Votre environnement de test est maintenant prêt à l’emploi !
