---
title: Créer un e-mail de bienvenue sur la fidélité - Défi
description: Créez un parcours qui envoie automatiquement un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau de fidélité.
kt: 8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: aaf273b8b6fe0a5f33c132cc0113ec2460152349
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 57%

---

# Créer un e-mail de bienvenue sur la fidélité - Défi

![E-mail de bienvenue relatif à la fidélité - Bannière de défis](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Défi | Créer un e-mail de bienvenue relatif à la fidélité |
|---|---|
| Utilisateurs | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=fr)</li> <li>[Qualification du segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=fr)</li><li>[Importer du contenu HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=fr)</li></ul> |
| Ressources à télécharger | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style=&quot;table-layout:auto&quot;}

## L’histoire

Luma propose un programme de fidélité pour attirer et fidéliser ses clients. Le programme offre quatre niveaux différents : bronze, argent, or et platine. Chaque niveau de fidélité reçoit différentes récompenses, remises et autres rémunérations spéciales en récompense de son activité récurrente.

Pour souligner le statut platine spécial, Luma souhaite envoyer un email de bienvenue aux clients lorsqu’ils atteignent le niveau platine.

## Votre défi

On vous a demandé de configurer un parcours qui envoie automatiquement un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau de fidélité platine.

>[!BEGINTABS]

>[!TAB Tâche]

Lorsqu&#39;un client fidèle se qualifie pour le niveau platine, il doit recevoir un email pour le féliciter et l&#39;informer de ses nouveaux avantages. L’équipe créative a fourni un fichier de HTML. **[Luma - mise à niveau de statut - eMail de bienvenue](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** avec le corps de l’email.

1. Créez un [!UICONTROL segment] dans Journey Optimizer appelé `Luma - platinum status`.

1. Créez un parcours appelé `Luma - New Status - platinum`.

   1. Un client passe sur le parcours lorsqu’il remplit les conditions requises pour le niveau de fidélité au platine.

   1. Le client ou la cliente doit recevoir un e-mail intitulé `Luma - Platinum Status - Welcome`, avec l’objet `Welcome to Platinum Status, {firstName}!` et le corps d’e-mail fourni par l’équipe créative. Il s’agit d’une [!UICONTROL transactionnel] e-mail.

   1. Lors du téléchargement du fichier HTML, vous remarquerez que l’e-mail fait référence au statut « diamant » plutôt qu’au statut « platine ». Au lieu de demander un nouveau fichier à l’équipe créative, mettez à jour l’e-mail dans le [!UICONTROL Concepteur d’e-mail].

>[!TAB Critères de réussite]

Testez votre parcours :

1. Assurez-vous que la variable [!UICONTROL Activité Lecture de segment] contient la variable [!UICONTROL namespace] défini sur **[!DNL Luma CRM id(lumaCrmId)]**.

1. Remplacer la valeur par défaut [!UICONTROL paramètres de messagerie électronique] et définissez-le sur votre propre adresse électronique :
   * Dans le **[!UICONTROL Paramètres de messagerie]**, cliquez sur le symbole T (activer le remplacement des paramètres).

   * Cliquez sur le bouton **[!UICONTROL Adresse]** champ .

   * Dans l’écran suivant, ajoutez votre adresse électronique entre parenthèses : `"yourname@yourdomain"` dans l’éditeur d’expression, puis cliquez sur **[!UICONTROL OK]**.

1. Définir le parcours en mode test.

1. Sélectionner **[!UICONTROL Déclenchement d’un événement]**.

1. Ajoutez ce qui suit : `CRM ID` pour `Stanleigh Stooke` dans le **[!UICONTROL Identifiant de profil]** field : `4f34057d9d9e792c28ba18ecae378e98`

**Résultat :** Vous devriez recevoir la personnalisation *Luma - État du platine - Bienvenue* e-mail.

Voici ce à quoi l’e-mail doit ressembler :

![Luma - mise à niveau de statut - eMail de bienvenue](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB Vérifier votre travail]

Voici à quoi le segment doit ressembler :

![Luma - Statut Platine - Segment](/help/challenges/assets/segment-luma-platinum-status.png)

Voici à quoi votre parcours doit ressembler :

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
