---
title: Créer un e-mail de bienvenue sur la fidélité - Défi
description: Créez un parcours qui envoie automatiquement un e-mail de bienvenue aux clientes et clients qui atteignent le niveau de fidélité.
jira: KT-8109
feature: Journeys
role: User
level: Beginner
last-substantial-update: 2023-02-01T00:00:00Z
exl-id: 6fd58b8e-7178-495d-a85d-eb67fc4f3acf
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: ht
source-wordcount: '403'
ht-degree: 100%

---

# Créer un e-mail de bienvenue sur la fidélité - Défi

| Défi | Créer un e-mail de bienvenue relatif à la fidélité |
|---|---|
| Utilisateurs | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=fr)</li> <li>[Qualification de segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/journeys/use-case-read-segment-qualification.html?lang=fr)</li><li>[Importer du contenu HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/email-channel/import-and-author-html-email-content.html?lang=fr)</li></ul> |
| Ressources à télécharger | [StatusUpgradeEmail.zip](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip) |

{style="table-layout:auto"}

## L’histoire

Luma propose un programme de fidélité pour attirer et fidéliser ses clients. Le programme offre quatre niveaux différents : bronze, argent, or et platine. Chaque niveau de fidélité reçoit différentes récompenses, remises et autres rémunérations spéciales en récompense de son activité récurrente.

Pour souligner le statut platine spécial, Luma souhaite envoyer un e-mail de bienvenue aux clientes et clients qui atteignent le niveau platine.

## Votre défi

On vous a demandé de configurer un parcours qui envoie automatiquement un e-mail de bienvenue aux clients lorsqu’ils atteignent le niveau de fidélité platine.

>[!BEGINTABS]

>[!TAB Tâche]

Lorsqu’un membre fidèle est éligible au niveau platine, un e-mail lui est envoyé pour la féliciter et l’informer de ses nouveaux avantages. L’équipe créative a fourni un fichier HTML **[Luma - Mise à niveau de statut - E-mail de bienvenue](/help/challenges/assets/email-assets/StatusUpgradeEmail.zip)** avec le corps de l’e-mail.

1. Créez un [!UICONTROL segment] dans Journey Optimizer appelé `Luma - platinum status`.

1. Créez un parcours appelé `Luma - New Status - platinum`.

   1. Une personne cliente passe par le parcours lorsqu’elle remplit les conditions requises pour le niveau de fidélité platine.

   1. Le client ou la cliente doit recevoir un e-mail intitulé `Luma - Platinum Status - Welcome`, avec l’objet `Welcome to Platinum Status, {firstName}!` et le corps d’e-mail fourni par l’équipe créative. Il s’agit d’un e-mail [!UICONTROL transactionnel].

   1. Lors du téléchargement du fichier HTML, vous remarquerez que l’e-mail fait référence au statut « diamant » plutôt qu’au statut « platine ». Au lieu de demander un nouveau fichier à l’équipe créative, mettez à jour l’e-mail dans le [!UICONTROL concepteur d’e-mail].

>[!TAB Critères de réussite]

Testez votre parcours :

1. Assurez-vous que l’[!UICONTROL Activité Lecture de segment] contient l’[!UICONTROL espace de noms] défini sur **[!DNL Luma CRM id(lumaCrmId)]**.

1. Remplacez les [!UICONTROL paramètres d’e-mail] par défaut et définissez-les sur votre propre adresse e-mail.
   * Dans les **[!UICONTROL paramètres d’e-mail]**, cliquez sur le symbole T (activer le remplacement des paramètres).

   * Cliquez sur le champ **[!UICONTROL Adresse]**.

   * Dans l’écran suivant, ajoutez votre adresse e-mail entre parenthèses, `"yourname@yourdomain"`, dans l’éditeur d’expression, puis cliquez sur **[!UICONTROL OK]**.

1. Définissez le parcours en mode test.

1. Sélectionnez **[!UICONTROL Déclencher un événement]**.

1. Ajoutez `CRM ID` pour `Stanleigh Stooke` dans le champ **[!UICONTROL Identifiant de profil]** : `4f34057d9d9e792c28ba18ecae378e98`.

**Résultat :** vous devriez recevoir l’e-mail personnalisé *Luma - Statut platine - E-mail de bienvenue*.

Voici ce à quoi l’e-mail doit ressembler :

![Luma - Mise à niveau de statut - E-mail de bienvenue.](/help/challenges/assets/status-upgrade-welcome-email.png)

>[!TAB Vérifier votre travail]

Voici à quoi le segment doit ressembler :

![Luma - Statut Platine - Segment](/help/challenges/assets/segment-luma-platinum-status.png)

Voici à quoi votre parcours doit ressembler :

![platinum-status-upgrade-journey](/help/challenges/assets/journey-luma-status-upgrade.png)

>[!ENDTABS]
