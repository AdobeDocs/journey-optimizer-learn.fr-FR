---
title: Défi lié au réapprovisionnement du produit
description: Appliquez vos connaissances en matière de création de segments et testez vos compétences.
kt: 8417
feature: Segments
role: User
level: Beginner
hide: true
exl-id: 305aaf4c-7f5d-4f6f-abeb-466208f1fe48
source-git-commit: 7ecbed1b722d7f05ffd4a7c7071358d993cb1392
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 69%

---

# Défi lié au réapprovisionnement du produit

| Défi | Réapprovisionnement du produit |
|---|---|
| Personne | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=fr)</li><li> [Importer et créer du contenu d’e-mail HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=en)</li><li>[Cas d’utilisation : lecture de segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=fr)</li> |
| Ressources à télécharger | [Fichier d’email de redémarrage de produit](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip) |

## L’histoire

Lorsque vous parcourez le site web Luma, les clients peuvent ajouter des produits qui les intéressent à une liste de souhaits, ce qui permet à Luma d’envoyer aux clients des messages marketing ciblés et des informations sur les produits.

## Votre défi

Luma vous demande d’implémenter un parcours dans Journey Optimizer qui avertit les client(e)s qui ont un élément sur leur liste de souhaits précédemment en rupture de stock, lorsque cet élément est de nouveau en stock. L’équipe créative vous fournit les [Fichier d’email de redémarrage de produit](/help/challenges/assets/email-assets/ProductRestockEmail.html.zip).

>[!BEGINTABS]

>[!TAB Tâche]

## 1. Définition du segment - Éléments de liste blanche en rupture de stock

Pour cibler les clients potentiels intéressés lors du redémarrage de produits, créez un segment composé de clients :

* Qui ont ajouté au moins un élément à sa liste de souhaits (utilisez le type d’événement : [!UICONTROL Commerce Save For Latest])
* Qui était en rupture de stock au cours des trois derniers mois (utiliser la quantité en stock = 0)
* et n’ont pas acheté l’article depuis.

>[!TIP]
>Excluez de tous les types d’événement Achats où le SKU correspond au SKU de la variable *Événement enregistrer pour plus tard*. Vous trouverez le champ dans le *Parcourir les variables* .

Nommez ce segment : `Out-of-stock-Wishlist`


### 2. Créer le parcours - Notification de réapprovisionnement du produit

Lorsqu’un article précédemment en rupture de stock est de nouveau en stock, avertissez les client(e)s qui ont ajouté un article en rupture de stock avec un appel de démarrage d’achat maintenant que l’article est de nouveau en stock.

1. Appelez le parcours : `Product Restock`
2. Le parcours doit être déclenché lorsqu’un produit est de nouveau en stock.
3. Envoyez la variable *Email de redémarrage de produit* to
4. utilisateurs et utilisatrices qui avaient ajouté cet élément à leur liste de souhaits alors qu’il était en rupture de stock.

>[!TAB Critères de réussite]

Testez votre parcours :

1. Assurez-vous que l’événement de segment lu comporte l’espace de noms = `Luma CRM ID`
1. Remplacez les paramètres d’e-mail par défaut et définissez-les sur votre propre adresse e-mail (voir e-mail #1 pour obtenir des instructions).
1. Définir le parcours en mode test
1. Déclencher un événement - Saisissez les données suivantes :

   * Description : Oubliez les machines fantaisistes et les adhésions coûteuses - Le kit de bandes de résistance et de renforcement Harmony Lumaflex est tout ce dont vous avez besoin pour faire une incroyable séance de sport. Le kit contient tout ce dont vous avez besoin pour une série d’exercices de renforcement et de tonification.
   * Nom : Kit de bandes de résistance et de renforcement Harmony Lumaflex.
   * Prix : 22.
   * ID de produit : 24-UG03.
   * URL de l’image du produit : https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/ug03-bk-0.jpSKU: 24-UG03
   * Type d’événement Stock : réapprovisonnement
   * Identifiant de profil : Jenna_Palmer9530@emailsim.io

Vous devriez recevoir l’e-mail « Réapprovisonnement des produits Luma » avec les détails du produit et la personnalisation pour Jenna.

>[!TAB Vérifier votre travail]

Voici à quoi votre segment doit ressembler :

![Segment - Éléments de liste de souhaits en rupture de stock](/help/challenges/assets/C1-S2.png)


Voici à quoi votre parcours doit ressembler :

![Parcours de réapprovisionnement du produit](/help/challenges/assets/c3-j3-journey.png)

Condition : dans une liste de souhaits.

![Condition - dans une liste de souhaits](/help/challenges/assets/c3-j3-condition.png)

Code de condition :

```in(@{LumaProductRestock._wwfovlab065.sku},#{ExperiencePlatform.ExperienceEvents.experienceevent.all(currentDataPackField.eventType=="commerce.saveForLaters").productListItems.all().SKU})```


>[!TIP]
> * Sélectionnez le SKU sous Enregistrer pour plus tard dans la section *Parcourir les variables*.
> * Utilisez l’option de comparaison lorsque vous déposez le SKU sous Enregistrer pour plus tard dans le champ d’événement.


Vérifiez le code dans le coin inférieur droit de l’écran Modifier le segment, sous Événements. Le code doit se présenter comme suit :

Code :
```(Include have at least 1 Save For Laters event where ((Stock Quantity equals 0)) THENExclude all  Purchases events where ((SKU equals Save For Laters1 SKU)) ) and occurs in last 3 month(s)```

>[!ENDTABS]

### Créer un e-mail - Réapprovisionnement produit Luma

Avertissez les client(e)s qui ont ajouté un article en rupture de stock avec un appel de démarrage d’achat maintenant que l’article est de nouveau en stock.



>[!TIP]
>
> Utilisez l’événement métier existant. Ajoutez une condition qui vérifie que le SKU du réapprovisionnement est inclus dans (n’importe quel) type d’événement save pour les laters.




