---
title: Créer un email de bienvenue relatif à l’état de fidélité - Défi
description: Découvrez les principes de base de création d’un parcours dans la zone de travail du parcours.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 52fb90247fa30d5b5c86d5a464d994e8e7075049
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 8%

---

# Créer un email de bienvenue relatif à l’état de fidélité - Défi

![AJO Loyalty status email de bienvenue - Bannière de défis](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Défi | Créer un email de bienvenue relatif à l’état de fidélité |
|---|---|
| Personne | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Création d’un contenu d’e-mail avec l’éditeur de messages](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-email-content-with-the-message-editor.html?lang=en)</li> <li>[Utilisation d’informations d’événement contextuelles pour la personnalisation](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-contextual-event-information-for-personalization.html?lang=en)</li><li>[Utilisation des fonctions helper pour la personnalisation](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/personalize-content/use-helper-functions-for-personalization.html?lang=en)</li></ul> |
| Ressources à télécharger | [Ressources de confirmation de commande](/help/challenges/assets/email-assets/order-confirmation-assets.zip) |

## L&#39;histoire

Luma propose un programme de fidélité pour attirer et fidéliser ses clients. Le programme offre quatre niveaux différents : Argent, or, platine et diamant.

Chaque niveau de fidélité reçoit différents niveaux ou récompenses, remises et autres incitations spéciales en récompense de leur activité récurrente.

Pour souligner le statut spécial du diamant. Luma souhaite envoyer un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau diamant.

## Votre défi

Vous avez été chargé de configurer un parcours qui envoie automatiquement un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau de fidélité au diamant.

>[!NOTE]
> Si vous travaillez dans un environnement de test de formation partagé, il est recommandé d’ajouter votre nom ou vos initiales en tant que préfixe au nom de tout élément que vous créez.

>[!BEGINTABS]

>[!TAB Tâche]

Envoyez un email lorsqu’un client fidèle se rend sur le niveau Diamant pour le féliciter et l’informer de ses nouveaux avantages. La variable

1. Créez un segment dans Journey Optimizer appelé **votre nom - Luma - État du diamant**
1. Créez un parcours déclenché lorsqu’un client passe au nouveau niveau de fidélité Diamond (en particulier lorsqu’il entre dans le segment défini pour un nouveau membre de niveau Diamond) pour envoyer l’e-mail &quot;Luma - New Status - Diamond - Transactional&quot;.

   1. Créez un email transactionnel intitulé `(your name)_Luma – New Status – Diamond – Transactional email message`.
   1. Donnez à l’email un objet `Welcome to Diamond Status, (recipient's first name)!`.
   1. Utilisation du fichier de HTML fourni **[DiamondStatusEmail.html](/help/challenges/assets/email-assets/DiamondStatusEmail.html)** pour le corps de l’email.

1. Une fois le parcours terminé, mettez-le en mode test et déclenchez le parcours à vous envoyer.  

### Créer un message électronique Luma - New Status - Diamond - Transactionnel

Créer un message de bienvenue

### **Parcours #3 - email de bienvenue de mise à niveau de l’état Diamant**


>[!TAB Critères de réussite]

Testez votre parcours:

1. Assurez-vous que l’événement de qualification de segment a l’espace de noms = E-mail
1. Remplacez les paramètres de courrier électronique par défaut et définissez-les sur votre propre adresse électronique.
1. Définir le parcours en mode test
1. Déclenchement d’un événement
1. Ajoutez l’adresse électronique suivante dans le champ Identifiant de profil : Jenna_Palmer9530@emailsim.io

Vous devriez recevoir l’e-mail personnalisé &quot;Luma - New Status- Diamond-Transactional&quot;.

>[!TAB Vérifier votre travail]

Voici à quoi votre parcours doit ressembler :

![Diamond-status-upgrade-parcours](/help/challenges/assets/journey-luma-diamond-status-upgrade.png)

>[!ENDTABS]
