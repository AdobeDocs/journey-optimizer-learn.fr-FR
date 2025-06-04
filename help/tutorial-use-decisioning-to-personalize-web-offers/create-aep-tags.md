---
title: Création de balises Adobe Experience Platform
description: Création d’audiences AJO en fonction des préférences d’investissement des utilisateurs (actions, obligations, CD)
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%

---

# Création de balises Adobe Experience Platform

Les balises Experience Platform sont configurées sur la page web pour charger le SDK web Adobe Experience Platform, ce qui permet à l’appel de l’API sendEvent de déclencher des expériences personnalisées. Cette configuration garantit que les bibliothèques côté client nécessaires sont correctement initialisées, ce qui permet une interaction en temps réel avec Adobe Journey Optimizer pour la diffusion d’offres.

1. Connectez-vous à Collecte de données .
1. Cliquez sur **[!UICONTROL Balises]** > **[!UICONTROL Nouvelle propriété]**.
1. Créez une balise Adobe Experience Platform appelée Service ECID.
1. Ajoutez les extensions suivantes à la balise :

   ![tags-extensions](assets/ecid-tag.png)

1. Configurez le SDK Web Adobe Experience Platform pour utiliser l’environnement approprié et le flux de données Financial Advisors créé dans le tutoriel précédent

   ![configuration-sdk-web](assets/web-sdk-configuration.png)

Aucune configuration supplémentaire n’est nécessaire pour les extensions principales et la couche de données client Adobe

## Création de l’élément de données

L’élément de données ECID dans les balises Experience Platform est créé uniquement à des fins de débogage et de test. L’élément de données permet aux développeurs d’afficher l’Experience Cloud ID attribué à la session de navigateur d’un utilisateur, ce qui peut aider à valider la combinaison d’identités et à s’assurer que les appels `sendEvent` sont associés au profil correct. Cet élément n’est pas nécessaire au fonctionnement de la personnalisation, mais il est utile lors de l’implémentation et de l’assurance qualité

![ecid](assets/ecid-data-element.png)


## Inclure les balises AEP dans la page HTML

Créez et publiez les balises Adobe Experience Platform.

Lorsqu’une propriété AEP Tags est publiée, Adobe vous fournit une balise de script que vous devez placer dans votre ``` <head>``` HTML ou au bas des balises ``` <body>```.

1. Accédez à la propriété Balises (service ECID) .

1. Cliquez sur Environnements, puis sur l’icône d’installation de l’environnement souhaité (par exemple, Développement, Évaluation, Production).

1. Notez le code incorporé.

   Ce code doit être placé juste avant la balise ```</body>``` de fermeture dans la page HTML.
