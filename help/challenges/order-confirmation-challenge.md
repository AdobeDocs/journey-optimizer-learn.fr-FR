---
title: Créer un e-mail de confirmation de commande
description: Tester vos connaissances sur la création et la personnalisation de messages transactionnels
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: ec86e2ac-081d-47aa-a948-007107baa2b4
source-git-commit: 70815c3cd30de22aad7ec667b8baf9b4c8642491
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 82%

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

Créez un parcours qui envoie un e-mail de confirmation de commande lorsqu’un(e) client(e) Luma termine une commande en ligne.

>[!BEGINTABS]

>[!TAB Tâche]

1. Créez un parcours appelé `Luma - Order Confirmation`.
2. Utilisez l’événement : `LumaOnlinePurchase`
3. Créez l’e-mail de confirmation de commande appelé `Luma - Order Confirmation` :

* Transactionnel de catégorie : veillez à sélectionner la surface de l’e-mail transactionnel.
* L’objet doit être personnalisé avec le prénom du ou de la destinataire et doit inclure l’expression « Merci pour votre achat ».
* Utilisez le modèle `Luma - Order summary` et modifiez-le :
   * Supprimez le `You may also like` sections
   * Ajouter le lien de désabonnement au bas de l&#39;email

L’e-mail doit être structuré comme suit :
<table>
<tr>
<td>
  <div>
     <strong>Section d’en-tête</strong>
      </div>
  </td>
  <td>
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
    <em>Hey {firstName}</em><p>
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
      <p>
      <li>Le prénom et le nom proviennent du profil.
      <li>Remplacez l’adresse codée en dur dans le modèle par le <b>adresse de livraison</b>
      <li>Les détails de l’adresse sont des attributs contextuels de l’événement (rue 1, ville, code postal, état).
      <li> Supprimez la remise, le total et l’arrivée.</p>
  </td>
  <td>
  <p> Adresse de livraison :</p>
      <em>{firstName} {lastName}<br>
     {Rue 1}<br>
     {City}, {State} {postalCode}<br></em></p>
  </td>
 <tr>
<td>
  <div>
     <strong>Section Détails de la commande</strong>
      </div>
       <p><li>Ajoutez cette section sous la section <b>Ship to</b> .
      </p><br>
      <p><b>Astuces :</b>
      <li>Utilisez le composant de structure "Colonne gauche 1:2" pour cette section
      <li>Il s’agit d’informations d’événement contextuelles.
      <li>Utilisez la fonction [!UICONTROL helper function]: [!UICONTROL Each].
      <li>Passez au format de l’éditeur de code pour ajouter les données contextuelles.
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
   * `Quantity`: 1
   * `Price Total:` 69
   * `Purchase Order Number:` 6253728
   * `SKU:` LLMH09
   * `City:` Washington
   * `Postal Code:` 20099
   * `State`: DC
   * `Street:` Terrasse de Thierer

Vous devriez recevoir l’e-mail de confirmation d’achat personnalisé, avec le produit spécifié.

* L’objet doit porter le prénom du profil de test : Leora.
* La section Détails de la commande doit être renseignée avec les détails de la commande que vous avez saisis lors du test.

>[!TAB Vérifier votre travail]

**Parcours**

![Parcours](/help/challenges/assets/c2-journey.png)


**E-mail**

**Objet :**

Merci pour votre achat, {{ profile.person.name.firstName }}!

Voici à quoi votre corps d’email doit ressembler :

![E-mail](//help/challenges/assets/c2-email.png)

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

Voici à quoi votre code doit ressembler :

En-tête :

```javascript
Order #: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

**Liste des produits :**

Utilisez la fonction d’assistance « each » pour créer la liste des produits. Affichez-les dans un tableau. Voici à quoi votre code doit ressembler (avec vos variables spécifiques, telles que votre ID d’événement, au lieu de `454181416` et votre organisation I au lieu de `techmarketingdemos` ) :

```javascript
{{#each context.journey.events.454181416.productListItems as |product|}}<tr> <th class="colspan33"><div class="acr-fragment acr-component image-container" data-component-id="image" style="width:100%;text-align:center;" contenteditable="false"><!--[if mso]><table cellpadding="0" cellspacing="0" border="0" width="100%"><tr><td style="text-align: center;" ><![endif]--><img src="{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.imageUrl}}" style="height:auto;width:100%;" height="233" width="233"><!--[if mso]></td></tr></table><![endif]--></div></th> <th class="colspan66"><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p><span style="font-weight:700;">{{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.name}}</span></p></div></div><div class="acr-fragment acr-component" data-component-id="text" contenteditable="false"><div class="text-container" contenteditable="true"><p>${{context.journey.events.454181416.productListItems.VYG__902489191a0a40e67f51f17f3ea9e2dfaf2dea3bd0bebe8b._techmarketingdemos.product.price}}.00</p><p>Quantity: {{context.journey.events.454181416.productListItems.quantity}}</p></div></div></th></tr> {{/each}}
```

**Prix total :**

Total :`${{context.journey.events.1627840522.commerce.order.priceTotal}}.00`


>[!ENDTABS]