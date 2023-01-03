---
title: Créer un e-mail de bienvenue sur la fidélité - Défi
description: Découvrez les principes de base de création d’un parcours dans la zone de travail du parcours.
kt: 8109
feature: Journeys
role: User
level: Beginner
hide: true
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 7a178b9c523ead0cf27aaa87d25b3752ef53f519
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 100%

---

# Créer un e-mail de bienvenue sur la fidélité - Défi

![E-mail de bienvenue relatif à la fidélité - Bannière de défis](/help/challenges/assets/email-assets/luma-transactional-onboarding-1.png)

| Défi | Créer un e-mail de bienvenue relatif à la fidélité |
|---|---|
| Utilisateurs | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=fr)</li> <li>[Qualification du segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment-qualification.html?lang=fr)</li><li>[Importer du contenu HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=fr)</li></ul> |
| Ressources à télécharger | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

## L’histoire

Luma propose un programme de fidélité pour attirer et fidéliser ses clients. Le programme offre quatre niveaux différents : bronze, argent, or et platine. Chaque niveau de fidélité reçoit différentes récompenses, remises et autres rémunérations spéciales en récompense de son activité récurrente.

Souligner le statut spécial du niveau platine. Luma souhaite envoyer un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau platine.

## Votre défi

On vous a demandé de configurer un parcours qui envoie automatiquement un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau de fidélité platine.

>[!BEGINTABS]

>[!TAB Tâche]

Lorsqu’un client ou une client fidèle se qualifie pour le niveau platine, il/elle doit recevoir un e-mail pour le/la féliciter et l’informer de ses nouveaux avantages. L’équipe créative a fourni un fichier HTML **[Luma - Mise à niveau de statut - E-mail de bienvenue](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** avec le corps de l’e-mail.

1. Créez un [!UICONTROL segment] dans Journey Optimizer appelé `Luma – status upgrade`.
2. Créez un parcours appelé `Luma – New Status – platinum`.
   1. Un client ou une cliente passe par le parcours lorsqu’il/elle remplit les conditions requises pour le niveau de fidélité platine.
   2. Le client ou la cliente doit recevoir un e-mail intitulé `Luma – Platinum Status - Welcome`, avec l’objet `Welcome to Platinum Status, (recipient's first name)!` et le corps d’e-mail fourni par l’équipe créative. Il s’agit d’un e-mail [!UICONTROL transactionnel].
   3. Lors du téléchargement du fichier HTML, vous remarquerez que l’e-mail fait référence au statut « diamant » plutôt qu’au statut « platine ». Au lieu de demander un nouveau fichier à l’équipe créative, mettez à jour l’e-mail dans le Concepteur d’e-mail.

>[!TAB Critères de réussite]

Testez votre parcours :

1. Assurez-vous que l’[!UICONTROL Activité Lecture de segment] contient l’[!UICONTROL espace de nom] défini sur **[!DNL Luma CRM id(lumaCrmId)]**.
2. Remplacez les [!UICONTROL paramètres d’e-mail] par défaut et définissez-les sur votre propre adresse e-mail.
   * Affichez les valeurs masquées en cliquant sur le symbole de l’œil.
   * Dans les [!UICONTROL paramètres d’e-mail], cliquez sur le symbole T (activer le remplacement du paramètre

       ![Remplacer les paramètres d’e-mail](/help/challenges/assets/c3-override-email-paramters.jpg)
   
   * Cliquez dans le [!UICONTROL champ d’adresse].
   * Dans l’écran suivant, ajoutez votre adresse e-mail entre parenthèses : `"yourname@yourdomain"` dans l’éditeur d’expression, puis cliquez sur ok.


3. Définir le parcours en mode test
4. Déclencher un événement
5. Ajoutez ce qui suit : [!DNL CRM ID] pour `Stanleigh Stooke` dans le champ [!UICONTROL Identifiant de profil] : `4f34057d9d9e792c28ba18ecae378e98`.

**Résultat :** vous devriez recevoir l’e-mail personnalisé *Luma - Statut platine - Bienvenue*.

>[!TAB Vérifier votre travail]

Voici à quoi votre parcours doit ressembler :

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)


Voici ce à quoi l’e-mail doit ressembler :

![Luma - Mise à niveau de statut - E-mail de bienvenue](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!ENDTABS]
