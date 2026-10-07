---
title: Création de balises Adobe Experience Platform
description: Création d’audiences AJO en fonction des préférences d’investissement des utilisateurs (actions, obligations, CD)
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 6823ce13-bc77-4e2b-89e0-606e403c15f2
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: a984631b-2bae-4860-9b15-69c41a799dcb
    internal-label: APIs and SDKs
subfeature_v2:
  - id: a7a194a0-75e2-4913-8a83-14714fbf68e6
    internal-label: Decisioning API
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '291'
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

Lorsqu’une propriété AEP Tags est publiée, Adobe vous fournit une balise de script que vous devez placer dans votre `<head>` HTML ou au bas des balises `<body>`.

1. Accédez à la propriété Balises (service ECID) .

1. Cliquez sur Environnements, puis sur l’icône d’installation de l’environnement souhaité (par exemple, Développement, Évaluation, Production).

1. Notez le code incorporé.

   Ce code doit être placé juste avant la balise `</body>` de fermeture dans la page HTML.
