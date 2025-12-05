---
source-git-commit: ab619c80bcc5df95af8e80c664c42e5c281bc648
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---
# Messages in-app

## Que sont les messages in-app ?

Les messages in-app apparaissent dans votre application mobile lorsqu’un utilisateur ou une utilisatrice est activement engagé(e). Ces messages de style recouvrement s’affichent sous la forme de bannières, de pop-ups ou de cartes directement sur le dessus de l’interface de l’application. Elles n’apparaissent pas sur l’écran de verrouillage ni en dehors de l’environnement de l’application.

Les messages in-app sont déclenchés par des actions ou des conditions spécifiques de l’utilisateur ou utilisatrice, telles que l’affichage d’un écran particulier, l’exécution d’un achat ou la qualification pour un segment ciblé.


Par exemple :

* Un jeu présentant un pop-up présentant une nouvelle fonctionnalité au moment où l’utilisateur ou l’utilisatrice la déverrouille.
* Application d’achat affichant une bannière avec un code de coupon lorsque l’utilisateur ou l’utilisatrice parcourt les produits.
* Application de réseau social suggérant de nouveaux comptes à suivre en fonction de l’activité actuelle

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

