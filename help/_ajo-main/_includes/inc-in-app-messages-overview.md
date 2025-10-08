---
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 1%

---
# Messages in-app

## Que sont les messages in-app ?

Les messages in-app sont des messages qui apparaissent dans une application lorsque l’utilisateur l’utilise activement. Il s’agit de messages de type recouvrement qui se trouvent sur le dessus de votre application. Elles ne s&#39;affichent pas sur l&#39;écran de verrouillage ou à l&#39;extérieur de l&#39;application, mais sous forme de bannières, de fenêtres contextuelles ou de petites cartes lorsque l&#39;utilisateur explore l&#39;application.

Les messages in-app sont déclenchés par des actions ou des conditions spécifiques de l’utilisateur ou utilisatrice, telles que l’affichage d’une certaine page, l’exécution d’un achat ou l’appartenance à un segment ciblé.


Par exemple :

* Un jeu peut afficher un pop-up expliquant une nouvelle fonctionnalité au moment où l’utilisateur la déverrouille.
* Une application d’achat peut afficher une bannière avec un code de coupon lorsque l’utilisateur parcourt les articles.
* Une application de réseau social peut afficher un message suggérant à l’utilisateur de suivre de nouveaux comptes.

## Cas d’utilisation

| **Avantages** | **Pourquoi** | **Exemples de cas d’utilisation** |
|----------------------------------|------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| Interaction client importante | Capture les utilisateurs lorsqu’ils sont actifs dans l’application, offrant ainsi une visibilité et une action accrues | <ul><li>Présentation de l’intégration</li><li>Annonces de fonctionnalités</li><li>Fenêtres contextuelles d’assistance en temps réel</li></ul> |
| Pertinent du point de vue contextuel | Permet de déclencher des messages par le comportement de l’utilisateur, en les rendant opportuns et personnalisés | <ul><li> montée en gamme après utilisation des fonctionnalités</li><li> Inactivité : coups de pouce</li><li> Messages d’erreur ou de succès</li></ul> |
| Diffusion en temps réel | Permet une communication immédiate pour les mises à jour urgentes ou critiques | <ul><li> Pannes système</li><li>Confirmations de transaction</li><li>Échecs de paiement</li></ul> |
| Aucune dépendance aux canaux externes | Permet de conserver l’expérience utilisateur contenue dans votre produit sans recourir aux e-mails/SMS | <ul><li> Rappels d’achèvement du tutoriel</li><li>Alertes d’expiration d’essai</li></ul> |
| Meilleur potentiel de conversion | Les messages placés dans le contexte sont mieux convertis que les messages hors plateforme | <ul><li> Met à niveau les invites après avoir atteint les limites du plan</li><li>Questionnaires in-app</li></ul> |
| Personnalisation et segmentation | Peut être personnalisé en fonction des données utilisateur ou des événements d’application | <ul><li> Messages adaptés au niveau de l’utilisateur ou au niveau d’activité</li><li> Alertes spécifiques au rôle </li></ul> |
| Non intrusif (bien conçu) | Permet une communication subtile mais efficace sans interrompre le flux utilisateur | <ul><li> Infobulles</li><li>Sélecteurs avec mises à jour</li><li>Bogues du widget de conversation</li></ul> |


## Si ce n *est pas* utiliser la communication in-app

* **L’utilisateur n’utilise pas activement l’application**\
  Les messages in-app ne s’affichent pas si l’utilisateur ou l’utilisatrice n’est pas actuellement connecté(e) ou n’utilise pas votre produit. Utilisez plutôt l’e-mail ou la notification push.
* **Problèmes critiques ou urgents nécessitant une attention immédiate**\
  Pour les messages urgents (par exemple, alertes de sécurité, échecs de paiement), utilisez des canaux qui peuvent atteindre l&#39;utilisateur en dehors de l&#39;application, tels que les SMS ou les e-mails.
* **Communications réglementaires ou juridiques**\
  Les messages liés à la conformité (par exemple, les mises à jour de termes, les modifications de politique) peuvent nécessiter une diffusion et une confirmation de lecture, ce qui est mieux adapté aux e-mails.
* **Réactivation de compte ou campagnes de reconquête**\
  Si l’utilisateur est inactif ou résilié, il ne verra pas les messages in-app. Utilisez des campagnes de réengagement par e-mail ou par notification push.
* **Mises à jour transactionnelles de gros volume**\
  Il est souvent préférable d’envoyer les notifications telles que les mises à jour ou les accusés de réception pour archivage et commodité.
* **Une utilisation excessive entraîne la cécité ou l’agacement des bannières**\
  Bombarder les utilisateurs et utilisatrices avec trop de messages in-app peut nuire à l’expérience utilisateur et entraîner une frustration ou des messages ignorés.
* **Pas de connectivité/scénarios hors ligne**\
  In-app repose sur le fait que l’utilisateur est en ligne et en session ; cela n’est d’aucune utilité dans les environnements où l’utilisateur est d’abord hors ligne.

