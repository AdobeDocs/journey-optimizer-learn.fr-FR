---
title: Créer un email de bienvenue relatif à l’état de fidélité - Défi
description: Découvrez les principes de base de création d’un parcours dans la zone de travail du parcours.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: e148101f8404c8e2019ee17823bcf1d7a9668bc5
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 4%

---

# Créer un email de bienvenue relatif à l’état de fidélité - Défi

![AJO Loyalty status email de bienvenue - Bannière de défis](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Défi | Créer un email de bienvenue relatif à l’état de fidélité |
|---|---|
| Personne | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html)</li> <li>[Qualification du segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html)</li><li>[Importer du contenu de HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html)</li></ul> |
| Ressources à télécharger | [platinumStatusEmail.zip](/help/challenges/assets/email-assets/platinumStatusEmail.zip) |

## L&#39;histoire

Luma propose un programme de fidélité pour attirer et fidéliser ses clients. Le programme offre quatre niveaux différents : Bronze, argent, or et platine. Chaque niveau de fidélité reçoit différents niveaux ou récompenses, remises et autres incitations spéciales en récompense de leur activité récurrente.

Pour souligner le statut spécial du platine. Luma souhaite envoyer un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau platine.

## Votre défi

On vous a demandé de configurer un parcours qui envoie automatiquement un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau de fidélité platine.

>[!BEGINTABS]

>[!TAB Tâche]

Lorsqu&#39;un client fidèle se qualifie pour le niveau platine, il doit recevoir et envoyer un email pour le féliciter et l&#39;informer de ses nouveaux avantages. L’équipe créative a fourni un fichier de HTML. **[Luma - mise à niveau de statut - eMail de bienvenue](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** avec le corps de l’email.

1. Créez un segment dans Journey Optimizer appelé `Luma – status upgrade`.
2. Créez un parcours appelé &quot;Luma - New Status - platine&quot;.
   1. Un client se déplace sur le parcours, lorsqu’il remplit les conditions requises pour le niveau de fidélité platine.
   2. Le client doit recevoir un e-mail intitulé `Luma – Platinum Status - Welcome`, avec l’objet `Welcome to Platinum Status, (recipient's first name)!` avec le corps fourni par l’équipe créative.
   3. Lors du téléchargement du fichier de HTML, vous remarquerez que l’email fait référence au statut &quot;diamant&quot; plutôt qu’à &quot;platine&quot;. Au lieu de demander un nouveau fichier à l’équipe créative, mettez à jour l’email dans le Concepteur d’email.

>[CONSEIL !]
> Assurez-vous que le message Luma - Platinum Status - Welcome eMail est transactionnel.


>[!TAB Critères de réussite]

Testez votre parcours:

1. Assurez-vous que l’espace de noms de l’activité Lecture de segment est défini sur **Luma CRM id(lumaCrmId)**
2. Remplacez les paramètres de courrier électronique par défaut et définissez-les sur votre propre adresse électronique.

+++ Cliquez ici pour plus d’informations sur la façon de remplacer
   * Affichez les valeurs masquées en cliquant sur le symbole de l’oeil.
   * Dans les paramètres de l’e-mail, cliquez sur le symbole T (activer le remplacement des paramètres).

   ![Remplacer les paramètres de courrier électronique](/help/challenges/assets/c3-override-email-paramters.jpg)

   * Cliquez dans le champ Adresse
   * Dans l’écran suivant, ajoutez votre adresse électronique entre parenthèses : `"yourname@yourdomain"` dans l’éditeur d’expression, puis cliquez sur ok.
+++


3. Définir le parcours en mode test
4. Déclenchement d’un événement
5. Ajoutez l’identifiant CRM suivant pour Stanleigh Stooke dans le champ Identifiant de profil : `4f34057d9d9e792c28ba18ecae378e98`

Vous devriez recevoir la personnalisation *Luma - État du platine - Bienvenue* e-mail.

>[!TAB Vérifier votre travail]

Voici à quoi votre parcours doit ressembler :

![platinum-status-upgrade-parcours](/help/challenges/assets/journey-luma-status-upgrade.png)


Voici à quoi l’email doit ressembler :

![Luma - mise à niveau de statut - eMail de bienvenue](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
