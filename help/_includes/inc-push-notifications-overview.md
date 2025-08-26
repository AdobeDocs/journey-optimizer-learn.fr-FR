---
source-git-commit: 6aa7b4c72ce5bd72002ad88ba88a20f32d54c360
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# Présentation des notifications push

## Que sont les notifications push ?

Les **notifications push** sont de courts messages qui s’affichent sur un téléphone, une tablette ou un ordinateur, même lorsque l’utilisateur n’utilise pas l’application qui les a envoyées. Ils sont un moyen pour les applications de « vous taper sur l&#39;épaule » et d&#39;attirer votre attention.

Par exemple :

* Une application d’achat peut vous alerter en cas de vente importante.
* Une application de livraison peut vous informer que votre commande est en cours de traitement.
* L&#39;application d&#39;une compagnie aérienne peut vous informer que votre vol est prêt à être enregistré.

**Important :** l’utilisateur doit donner l’autorisation (opt-in) à l’application avant de pouvoir vous envoyer des notifications push. Cela se produit généralement lorsque l’application est ouverte pour la première fois après l’avoir téléchargée, ou plus tard si l’application pose à nouveau la question lors de son utilisation. Sans l’autorisation de l’utilisateur, l’application ne peut pas envoyer de notifications push à son appareil.

## Cas d’utilisation

Choisissez les notifications push comme canal de messagerie préféré lorsque vous devez :

| # | Avantage | Pourquoi | Exemples de cas d’utilisation |
|---|---------|-----|-------------------|
| 1 | Mises à jour sensibles à l’heure | Les messages push peuvent apparaître sur l’écran de verrouillage ou sous forme de bannières sans que l’utilisateur ait à ouvrir l’application. | <ul><li> Alertes urgentes (pannes de service, avertissements de sécurité)</li><li>Offres sensibles au facteur temps (ventes flash)</li><li> Mises à jour en temps réel (scores sportifs, diffusion des commandes)</ul> |
| 2 | Réengagement | Les notifications push peuvent ramener les utilisateurs inactifs dans l’application en fournissant des invites personnalisées et pertinentes. | <ul><li> Rappels de panier ou de navigation abandonnés (par exemple, « Vous avez laissé des articles dans votre panier ») : passez en caisse maintenant pour 10 % de réduction.</li></ul> |
| 3 | Réduction de la dépendance à l’égard de canaux plus coûteux | Les notifications push sont généralement gratuites une fois que vous avez créé l’infrastructure, contrairement aux SMS ou aux e-mails, qui entraînent des coûts par message. | <ul><li> Utilisez des notifications push plutôt que des SMS payés pour les mises à jour fréquentes.</li></ul> |
| 4 | Diffuser du contenu riche et interactif | Les API push modernes permettent d&#39;envoyer des images, des vidéos, des actions rapides (par exemple, « Accepter » / « Refuser ») ou des liens profonds vers des écrans d&#39;application spécifiques. | <ul><li>Campagnes marketing avec un attrait visuel</li><li>Actions rapides de l’utilisateur sans ouvrir complètement l’application.</li></ul> |
| 5 | Utilisation des fonctionnalités natives de l’appareil | Les notifications push s’intègrent aux fonctionnalités du système d’exploitation iOS/Android telles que les vibrations, les sons, les badges et les déclencheurs de géorepérage. | <ul><li> Offres basées sur la localisation à proximité d’un magasin</li><li> Rappels déclenchés à des moments spécifiques.</li></ul> |
| 6 | Quand l’opt-in est probable | La notification push ne fonctionne que pour les utilisateurs ayant explicitement accepté l’extension. Si l&#39;application offre une valeur élevée ou si la marque a déjà confiance, les taux d&#39;opt-in peuvent être élevés. | <ul><li> Applications avec bases d’utilisateurs fidèles</li><li> Flux d’intégration qui expliquent la valeur des notifications.</li></ul> |

## Si ce n’est *le cas* utiliser la notification push comme canal principal.

* Faibles taux d’opt-in ou résistance des utilisateurs aux notifications.
* Nécessité d’un contenu de forme longue (l’e-mail peut être préférable).
* Informations sensibles ou hautement privées (les notifications push sont visibles sur les écrans verrouillés).
* Les utilisateurs se trouvent principalement sur le bureau et non dans l’application mobile.
