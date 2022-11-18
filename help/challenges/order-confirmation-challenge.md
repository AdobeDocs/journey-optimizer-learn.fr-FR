---
title: Créer une confirmation de commande
description: Tester vos connaissances sur la création et la personnalisation de messages transactionnels
kt: 7531
feature: Journeys
role: User
level: Beginner
hide: true
source-git-commit: dd2832c1e99ed9b8407a0aa9356335d3bce40622
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 4%

---


# Créer un email transactionnel de confirmation de commande

![Confirmation de commande](/help/challenges/assets/email-assets/luma-transactional-order-confirmation.png)

| Défi | Créer un email transactionnel de confirmation de commande |
|---|---|
| Personne | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Création d’un contenu d’e-mail avec l’éditeur de messages](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Utilisation d’informations d’événement contextuelles pour la personnalisation](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Utilisation des fonctions helper pour la personnalisation](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Ressources à télécharger | [Ressources de confirmation de commande](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## L&#39;histoire

Luma lance sa boutique en ligne et souhaite garantir une bonne expérience client en proposant un email de confirmation de commande une fois qu’un client a passé une commande.

Créez et personnalisez un message de confirmation de commande transactionnelle.

## Avez-vous tout ce dont vous avez besoin ?

## Votre défi

Créez un email de confirmation de commande qui est déclenché lorsqu’un client Luma termine une commande en ligne.

### Créer l&#39;email de confirmation de commande

Créez un nouveau message électronique intitulé &quot;(votre nom)_Luma - Confirmation de commande&quot;. L’objet doit être personnalisé avec le prénom du destinataire et doit inclure l’expression &quot;Merci pour votre achat&quot;.

En suivant les directives de la marque Luma, l’email doit être structuré comme suit :

<table>
<tr>
<td>
  <div>
     <strong> Section d’en-tête</strong>
      </div>
  </td>
  <td>
    <strong>Logo Luma</strong>
      <p>
     <li>luma_logo.png</li>
    <li>Taille 35 %, arrière-plan blanc centré </li>
    <li>Il doit comporter un lien vers le site web luma : https://publish1034.adobedemo.com/content/luma/us/en.html</li>
    <p>
    Conseil : Vous trouverez toutes les images appelées images de messages dans le dossier assets. <p>
    </td>
  </tr>
  <tr>
  <td>
  <div>
    <strong>Section de confirmation de commande
    </strong>
  </td>
  <td>
    <strong>Image</strong><p>
    <li>luma-transactional-order-confirmation-2.jpg </li>
    <li>Marge : Haut, bas (10)<div>
    <p>
    <strong>Texte</strong><p>
    <em>Merci pour l'achat !</em><p>
    <li>Alignement : left  </li>
   <li>Couleur du texte : rgb(101, 106, 119); font-size:14px</li>
    <li>Marge intérieure : left (95), right (95)</li><div>
    <p>
     <em>Votre commande a été passée.
    <p>Une fois votre package livré, nous vous enverrons un email avec un numéro de tracking afin que vous puissiez tracker votre commande.</p></em>
    </strong><p>
    <li>Alignement : left  </li>
    <li>Couleur du texte : rgb(101, 106, 119); font-size:14px </li>
    <li>Marge intérieure : left (95), right (95)</li><div>
    </a>
    <p>
    <strong>Bouton:</strong>
   <p><em>Afficher votre commande</em></p>
      <li>Couleur d’arrière-plan : rgb(25, 121, 195)</li>
      <li>Couleur du texte : Blanc</li>
      <li>Aucune bordure</li>
      <li>Hauteur : 40</li>
      <li>Ajouter un lien vers un site web de votre choix </li>
      <li>Aligne le texte à gauche au-dessus (Conseil : utiliser la marge du conteneur)</li>
  </td>
 <tr>
<td>
  <div>
     <strong>Section Détails de la commande</strong>
      </div>
      <p>Astuces:
      <li>Il s’agit d’informations d’événement contextuelles. Vous ne pourrez ajouter le message dans le contexte qu’une fois que vous aurez ajouté le message à votre parcours (voir l’étape 2). Ne publiez pas votre email avant de l'avoir ajouté au Parcours et de l'avoir modifié avec les informations d'événement contextuel !</li>
      <li>Utilisez la fonction d’assistance : Chaque</li>
      <li>Utilisez le format de l’éditeur de HTMLS pour les données contextuelles. Placez les informations dans des conteneurs à l’aide de balises DIV.</li>
  </td>
  <td>
    <strong>En-tête</strong>
    <p>
    <em>Commande {Purchase Order Number}</em>
    </p>
    <strong>Liste des produits commandés :
  </strong>
  <p>Chacun des éléments doit être formaté comme suit :
   <img alt="ordre" src="./assets/c2-order.png"> 
</p>
<strong>Image du produit :</strong>
<li>Classe : cart-item-chair
<li>style : border-box: min-height:40 px</li>
<li>marge intérieure supérieure et inférieure : 20 px</li>
<li>remplissage-gauche:80px</li>
<li>border-radius:0px</li>
<li>Utiliser comme image d’arrière-plan pour le conteneur</li>
<li>background-position: 0 % 50 %</li>
<li>background-size: 60 px</li>
<li>background-repeat : no-repeat</li>
<p>
<strong>Prix:</strong>
<li>Format = H5</li>
<li>style = taille de boîte:bordure-box</li>
<li>margin-bottom:5px</li>
<li>margintop:0px;</li>
<p>
<strong>Nom et quantité :</strong>
<li>class=text-small</li>
<li>style=taille des cases : border-box</li>
<li>padding-top : 5px</li>
<li>color: rgb(101, 106, 119)</li>
<li>font-size:14px</li>
<p>
</td>
  </tr>
</table>

### Création du parcours

1. Appelez le parcours &quot;votre nom _Luma-Order Confirmation&quot;.
1. Utilisez l’événement : LumaOnlinePurchase
1. Action : Ajout du message que vous avez créé à l’étape 1
1. Revenez au message et ajoutez les attributs contextuels
1. Publier l&#39;email

>[!TIP]
>
>Pour vous permettre de résoudre les problèmes de vos parcours, il est recommandé d’ajouter un autre chemin à toutes les actions de message en cas d’expiration ou d’erreur.

+++Critères de réussite

Déclenchez le Parcours que vous avez créé en mode test et envoyez-le vous-même :

1. Afficher les valeurs masquées en cliquant sur le symbole de l’oeil :
   1. Dans les paramètres de l’e-mail, cliquez sur le symbole T (activer le remplacement des paramètres).
      ![Remplacer les paramètres de courrier électronique](/help/challenges/assets/c3-override-email-paramters.jpg)
   2. Cliquez dans le champ Adresse
   3. Dans l’écran suivant, ajoutez votre adresse électronique entre parenthèses : *yourname@yourdomain* dans l’éditeur d’expression, puis cliquez sur ok.
2. Mise du parcours en mode test
3. Déclenchez l’événement avec les paramètres suivants :
   * Définissez l’identifiant de profil sur : Jenna_Palmer9530@emailsim.io
   * Type d’événement : commerce.purchases
   * Nom : Sprite Yoga Companion Kit
   * Quantité : 1
   * Total du prix : 61
   * Numéro de commande : 6253728
   * SKU : 24-WG080
   * productImageURL : <https://publish1034.adobedemo.com/content/dam/luma/en/products/gear/fitness-equipment/luma-yoga-kit-2.jpg>

Vous devriez recevoir l’e-mail de confirmation d’achat personnalisé, avec le produit spécifié.

* La ligne d’objet doit commencer par le prénom de votre profil de test : Jenna
* La section Détails de la commande doit être renseignée avec les détails de la commande que vous avez saisis lors du test.
* Les informations sur les clients doivent comporter le code de ville et postal de votre profil de test :

   43913 Thierer Terrace, Washington DC 2009

+++

+++Vérifiez votre travail

**Objet:**

{{ profile.person.name.firstName }}, merci pour votre achat !

**Section En-tête et confirmation :**

![Confirmation d’en-tête et de commande](/help/challenges/assets/c2-header.png)

**Section Détails de la commande :**

![Section Détails de la commande](/help/challenges/assets/c2-order-detail-section.png)

Voici à quoi votre code doit ressembler :

Header:

```javascript
Order: {{context.journey.events.1627840522.commerce.order.purchaseOrderNumber}}
```

Liste des produits :

Utilisez la fonction d’assistance &quot;each&quot; pour créer la liste des produits. Voici à quoi votre code doit ressembler :

```javascript
{{#each context.journey.events.1911672547.productListItems as|product|}}
<div class="cart-item-chair" style="box-sizing:border-box;min-height:40px;padding-top:20px;padding-bottom:20px;padding-left:80px;border-radius:0px;background-image:url({{product._wwfovlab065.productImageURL}});background-position:0% 50%;background-size:60px;background-repeat:no-repeat;">
<h5 style="box-sizing:border-box;margin-bottom:5px;font-size:16px;line-height:20px;margin-top:0px;">${{product.priceTotal}}.00</h5>
<div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">{{product.name}}</div><div class="text-small" style="box-sizing:border-box;padding-top:5px;color:rgb(101, 106, 119);font-size:14px;">Quantity: {{product.quantity}}</div></div><div class="divider-small" style="box-sizing:border-box;height:1px;margin-top:10px;margin-bottom:10px;background-color:rgb(209, 213, 223);"> </div>
{{/each}}

Total: ${{context.journey.events.1627840522.commerce.order.priceTotal}} 
```

**Section Informations client**

![Adresse client](assets/c2-customer-information.png)

La personnalisation doit se présenter comme suit :

```javascript
{{profile.homeAddress.street1}}
{{profile.homeAddress.city}},{{profile.homeAddress.state}} {{profile.homeAddress.postalCode}}
```

**Pied de page :**
![pied de page](/help/challenges/assets/c2-footer.png)

**Parcours**

![Parcours](/help/challenges/assets/c2-journey.png)

+++

