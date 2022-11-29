---
title: Défi lié au réapprovisionnement du produit
description: Appliquez ce que vous avez appris sur la création de segments et testez vos compétences.
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 8a2062f0719e799dd2d039488e6bba943fb458c4
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---

# Défi lié au réapprovisionnement du produit

| Défi | Réapprovisionnement du produit |
|---|---|
| Personne | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-segments.html?lang=en)</li><li> [Importation et création de contenu d’e-mail HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/import-and-author-html-email-content.html?lang=en)</li><li>[Cas d’utilisation : lecture de segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Ressources à télécharger | [Fichiers d’email de collection saisonnière](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## L&#39;histoire

Lorsque vous parcourez le site web Luma, les clients peuvent ajouter à une liste de souhaits des produits qui les intéressent. Cela permet à Luma d’envoyer aux clients des messages marketing ciblés et des informations sur les produits.

## Votre défi

Luma vous demande de mettre en oeuvre un parcours dans Journey Optimizer qui avertit les clients qui ont un élément sur leur liste de souhaits précédemment en rupture de stock, lorsque cet élément est de nouveau en stock.

## Définition du segment - Éléments de liste blanche en rupture de stock

Pour cibler les clients potentiels intéressés lors du redémarrage de produits, créez un segment qui se compose de clients

* Qui ont ajouté au moins un élément à sa liste de souhaits (type d’événement Utiliser : [!UICONTROL Commerce Save For Latest])
* Lequel **en rupture de stock** au cours des 3 derniers mois (utiliser quantité en stock = 0)
* Et n’ont pas acheté l’article depuis.

Nommez ce segment : *votre nom - Liste d&#39;attente en rupture de stock*

+++**VÉRIFIER VOTRE TRAVAIL**

Voici à quoi votre segment doit ressembler :

![Segment - Éléments de liste blanche en rupture de stock](/help/challenges/assets/C1-S2.png)

Clients ayant ajouté à leur liste de souhaits un article en rupture de stock au cours des 3 derniers mois :

* Événement : Enregistrer pour plus tard
   * Inclure au moins 1
   * Lorsque la quantité de stock est 0

et n’ont pas acheté l’article depuis :

* Excluez de tous les types d’événements Achats où le SKU correspond au SKU de la variable **Enregistrer pour un événement ultérieur**.

>[!TIP]
> * Sélectionnez le SKU sous Enregistrer pour plus tard dans la *Parcourir les variables* section
> * Utilisez l’option de comparaison lorsque vous déposez le SKU sous Enregistrer pour plus tard dans le champ d’événement.


Vérifiez le code dans le coin inférieur droit de l’écran Modifier le segment, sous Événements. Le code doit se présenter comme suit :

Code:
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

+++

### Créer un email - Réapprovisionnement Luma-Produit

Avertissez les clients qui ont ajouté un article en rupture de stock avec un appel de démarrage d’achat maintenant que l’article est de nouveau en stock.

### Création du parcours - Notification de réapprovisionnement du produit

Lorsqu’un article précédemment en rupture de stock est de nouveau en stock, avertissez les clients qui ont ajouté un article en rupture de stock avec un appel pour commencer à faire leurs achats maintenant que l’article est de nouveau en stock.

1. Créez un parcours appelé &quot;your name_Luma - Product Restock (votre nom_Luma - Référencement de produit)
1. Le parcours doit être déclenché lorsqu’un produit est de nouveau en stock.
1. Envoyez la variable *Réapprovisionnement Luma-Produit* envoyer par courrier électronique à
1. Utilisateurs qui avaient ajouté cet élément à leur liste de souhaits alors qu&#39;il était en rupture de stock

>[!TIP]
>
> Utilisez l’événement professionnel existant. Vous devez ajouter une condition qui vérifie que le SKU du réapprovisionnement est inclus dans (n’importe quel) type d’événement enregistré pour les laters.

+++**CRITÈRES DE RÉUSSITE**

Testez votre parcours:

1. Assurez-vous que l’événement de qualification de segment a l’espace de noms = E-mail
1. Remplacez les paramètres de courrier électronique par défaut et définissez-les sur votre propre adresse électronique (voir #1 de courrier électronique pour obtenir des instructions).
1. Définir le parcours en mode test
1. Déclencher un événement : saisissez les données suivantes :

   * Description : Oubliez les machines fantaisistes et les adhésions coûteuses - le kit Harmony Lumaflex Strength Band Kit est tout ce dont vous avez besoin pour faire une incroyable séance de sport. Le kit contient tout ce dont vous avez besoin pour une gamme d&#39;exercices de renforcement et de tonte.
   * Nom : Harmony Lumaflex Strength Band Kit
   * Prix : 22
   * ID de produit : 24-UG03
   * URL de l’image du produit : https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * Type d’événement Stock : restock
   * Identifiant de profil : Jenna_Palmer9530@emailsim.io

Vous devriez recevoir l’e-mail &quot;Rafraîchissement des produits Luma Email&quot; avec les détails du produit et la personnalisation pour Jenna.

+++

+++**VÉRIFIER VOTRE TRAVAIL**

Voici à quoi votre parcours doit ressembler :

![Parcours de réapprovisionnement du produit](/help/challenges/assets/c3-j3-journey.png)

Condition : Dans une liste bloquée

![Condition - dans la liste bloquée](/help/challenges/assets/c3-j3-condition.png)

Code de condition :

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```

+++
