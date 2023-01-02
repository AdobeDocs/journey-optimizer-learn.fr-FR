---
title: Créer un e-mail de confirmation de commande
description: Tester vos connaissances sur la création et la personnalisation de messages transactionnels
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 4268144ade6588e48fc38cae7e542c227af96827
workflow-type: ht
source-wordcount: '686'
ht-degree: 100%

---


# Créer un e-mail de confirmation de commande

![Confirmation de commande](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Défi | Créer un e-mail transactionnel de confirmation de commande |
|---|---|
| Utilisateurs | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer un contenu d’e-mail avec l’éditeur de messages](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=fr)</li> <li>[Utiliser des informations d’événement contextuelles pour la personnalisation](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=fr)</li><li>[Utiliser des fonctions d’assistance pour la personnalisation](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=fr)</li></ul> |
| Ressources à télécharger | [Ressources de confirmation de commande](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## L’histoire

Luma lance sa boutique en ligne et souhaite garantir une bonne expérience client en proposant un e-mail de confirmation de commande une fois qu’un(e) client(e) a passé une commande.



## Votre défi

Créez un parcours qui envoie un e-mail de confirmation de commande lorsqu’un(e) client(e) Luma termine une commande en ligne. Luma

>[!BEGINTABS]

>[!TAB Tâche]

1. Créez un parcours appelé `Luma - Order Confirmation`.
2. Utilisez l’événement : `LumaOnlinePurchase` comme déclencheur.
3. Créez l’e-mail de confirmation de commande appelé `Luma - Order Confirmation` :

* Transactionnel de catégorie : veillez à sélectionner la surface de l’e-mail transactionnel.
* L’objet doit être personnalisé avec le prénom du ou de la destinataire et doit inclure l’expression « Merci pour votre achat ».
* Utilisez le modèle `Luma - Order summary` et modifiez-le :

L’e-mail doit être structuré comme suit :
<table>
<tr>
<td>
  <div>
     <strong>Section d’en-tête</strong>
      </div>
  </td>
  <td>
    <strong>Logo Luma</strong>
      <p>
     <li>luma_logo.png</li>
    <li>Il doit comporter un lien vers le site web luma : https://publish1034.adobedemo.com/content/luma/us/en.html.</li>
    <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>Section de confirmation de commande</strong>
  </td>
  <td>
    <p>
    <strong>Texte</strong><p>
    <em>Bonjour {prénom}</em><p>
    <li>Alignement : gauche  </li>
   <li>Couleur du texte : rgb(69, 97, 162) #4461a2; 
   <li>font-size : 20px</li>
   <div>
    <p>
     <em>Votre commande a été passée.
    <p>Une fois votre paquet envoyé, nous vous enverrons un e-mail avec un numéro de suivi afin que vous puissiez suivre votre commande.</p></em>
    </strong>
    </tr>
  </td>
 <td>
  <div>
     <strong>Section Adresse de livraison</strong>
      </div>
      <p><li>Remplacez l’adresse codée en dur du modèle par l’adresse de livraison. 
      <li>Les détails de l’adresse sont des attributs contextuels de l’événement (rue, ville, code postal, état).
      <li>Le prénom et le nom proviennent du profil.
      <li> Supprimez la remise, le total et l’arrivée.</p>
  </td>
  <td>
  <p> Adresse de livraison :</p>
      <em>Prénom Nom<br>
Adresse</em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>Section Détails de la commande</strong>
      </div>
       <p><li>Ajoutez cette section après la section <b>Adresse de livraison</b> et le bouton <b>Afficher la commande</b>.
      </p><br>
      <p><b>Astuces :</b>
      <li>Il s’agit d’informations d’événement contextuelles.
      <li>Utilisez la fonction [!UICONTROL helper function]: [!UICONTROL Each].
      <li>Passez au format de l’éditeur de code pour ajouter les données contextuelles.
      <li>Placez les informations dans des conteneurs à l’aide de balises DIV.
  </td>
  <td>
    <strong>En-tête</strong>
    <p>
    <em>Commande : `purchaseOrderNumber`</em>
    </p>
    <strong>Liste des produits commandés :
</strong>
  <p>Chacun des éléments doit être formaté comme suit :
<img alt="commande" src="./assets/c2-order.png"> 
</p>
<strong>Image du produit :</strong>
<li>class : cart-item-chair
<li>style: border-box: min-height : 40px</li>
<li>Marge intérieure supérieure et inférieure : 20px</li>
<li>padding-left : 80px</li>
<li>border-radius : 0px</li>
<li>Utiliser comme image d’arrière-plan pour le conteneur.</li>
<li>Position de l’arrière-plan : 0 % 50 %</li>
<li>background-size : 60px</li>
<li>Répétition de l’arrière-plan : aucune répétition</li>
<p>
<strong>Prix :</strong>
<li>Format = H5</li>
<li>style=box-sizing : border-box</li>
<li>margin-bottom : 5px</li>
<li>margin-top : 0px;</li>
<p>
<strong>Nom et quantité :</strong>
<li>class=text-small</li>
<li>style=box-sizing : border-box</li>
<li>padding-top : 5px</li>
<li>color : rgb(101, 106, 119)</li>
<li>font-size : 14px</li>
<p>
</td>
  </tr>
</table>


>[!TIP]
>
>Pour vous permettre de résoudre les problèmes de vos parcours, il est recommandé d’ajouter un autre chemin d’accès à toutes les actions de message en cas d’expiration ou d’erreur.

>[!TAB Critères de réussite]

Déclenchez le parcours que vous avez créé en mode test et envoyez l’e-mail à vous-même :

1. Affichez les valeurs masquées en cliquant sur le symbole de l’œil :
   1. Dans les paramètres de l’e-mail, cliquez sur le symbole T (activez le remplacement des paramètres).
      ![Remplacer les paramètres d’e-mail](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Cliquez dans le champ Adresse.
   3. Dans l’écran suivant, ajoutez votre adresse e-mail entre parenthèses : *votrenom@votredomaine* dans l’éditeur d’expression, puis cliquez sur ok.
2. Mettez le parcours en mode test.
3. Déclenchez l’événement avec les paramètres suivants :
   * Définissez l’identifiant de profil sur : valeur d’identité :`a8f14eab3b483c2b96171b575ecd90b1`
   * Type d’événement : commerce.purchases
   * Nom : Sprite Yoga Companion Kit
   * Quantité : 1
   * `Price Total:` 61
   * `Purchase Order Number:` 6253728
   * `SKU:` 24-WG080
   * `productImageURL:` <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>
   * `City:` San José
   * `Postal Code:` 95110
   * `State` : Californie
   * `Street:` 345 Park Avenue

Vous devriez recevoir l’e-mail de confirmation d’achat personnalisé, avec le produit spécifié.

* L’objet doit porter le prénom du profil de test : Leora.
* La section Détails de la commande doit être renseignée avec les détails de la commande que vous avez saisis lors du test.

>[!TAB Vérifier votre travail]

**Parcours**

![Parcours](/help/challenges/assets/c2-journey.png)


**E-mail**

**Objet :**

{{ profile.person.name.firstName }}, merci pour votre achat !

**Section Adresse de livraison :**

Voici à quoi votre code doit ressembler :

```javascript
{{ profile.person.name.firstName }} {{ profile.person.name.lastName }}
{{context.journey.events.454181416.commerce.shipping.address.street1}}
{{context.journey.events.454181416.commerce.shipping.address.city}}, {{context.journey.events.454181416.commerce.shipping.address.state}} {{context.journey.events.454181416.commerce.shipping.address.postalCode}}
```

*event.45481416* sera un nombre différent pour vous.

CONSEIL : personnalisez chaque ligne séparément.

**Section Détails de la commande :**

![Section Détails de la commande](/help/challenges/assets/c2-order-detail-section.png)

Voici à quoi votre code doit ressembler :

En-tête :

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**Liste des produits :**

Utilisez la fonction d’assistance « each » pour créer la liste des produits. Affichez-les dans un tableau. Voici à quoi votre code doit ressembler :

```javascript
<div class="text-container" contenteditable="true">
  <p><span class="acr-expression-field" contenteditable="false">{{#each context.journey.events.454181416.productListItems as |product|}}
    </span></p>
  <div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
    <h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</h5>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</div>
    <div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div>
  </div>
  <div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
  {{/each}}<p></p>
  <p></p>
</div>
```

**Prix total :**

Total :`${{context.journey.events.1627840522.commerce.order.priceTotal}}`

**Section Informations sur le ou la client(e)**

![Adresse du ou de la client(e)](assets/c2-customer-information.png)

La personnalisation doit se présenter de la manière suivante :

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

>[!ENDTABS]