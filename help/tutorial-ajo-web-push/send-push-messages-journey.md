---
title: Envoyer des messages push dans un parcours
description: Le capping de la fréquence dans Adobe Journey Optimizer est appliqué au niveau de l’offre individuelle et repose sur la capture des événements d’impression et de clic de l’offre. Cela nécessite le suivi des événements decisioning.propositionDisplay et decisioning.propositionInteract à l’aide d’Adobe Web SDK et leur mappage à un schéma d’événement d’expérience XDM mis à jour dans Adobe Experience Platform.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2026-01-21T00:00:00.000Z
jira: KT-18526
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
source-wordcount: '389'
ht-degree: 0%
---
# Envoyer des messages push dans un parcours

Le déclenchement d’un parcours en fonction d’un événement de chute de prix permet un engagement en temps réel et axé sur le comportement avec les utilisateurs. Dans des scénarios réels, cet événement provient généralement d’un système de tarification principal lorsque le prix d’un produit est mis à jour. Dans ce tutoriel, nous simulons ce comportement en envoyant un événement price.drop personnalisé par le biais de la couche de données Adobe à l’aide de balises AEP, y compris des détails du produit tels que le nom et le SKU. Cet événement est ingéré dans Adobe Experience Platform et utilisé comme déclencheur d’entrée pour un parcours dans Adobe Journey Optimizer. Une fois reçu, le parcours peut envoyer immédiatement une notification push personnalisée aux utilisateurs et utilisatrices éligibles, les informant de la baisse du prix et les encourageant à agir en temps opportun.

Le déclenchement d’un parcours à l’aide d’un événement personnalisé implique les étapes suivantes

## Création d’un événement personnalisé dans Journey Optimizer

Connectez-vous à Adobe Journey Optimizer et accédez à Administration → Configurations → Événements, puis sélectionnez Créer un événement. Créez un événement nommé PriceDropEvent et associez-le au schéma d’événement SchemaForPushNotification créé précédemment dans le tutoriel. Assurez-vous que les propriétés de l’événement sont configurées comme illustré dans l’image de référence.

![event-properties](assets/price-drop-event.png)

Dans le schéma , sélectionnez les champs requis pour les rendre disponibles pour la personnalisation. Plus précisément, incluez les `Name` et `SKU` de l’objet ProductListItems, ainsi que l’identifiant de l’identityMap. Ces champs seront ensuite accessibles dans l’éditeur de personnalisation, ce qui vous permettra de composer dynamiquement les messages de notification push en fonction du produit et du contexte utilisateur.

## Création d’une propriété de balise

Cette propriété est configurée avec AEP Web SDK, qui est connecté au WebPushDataStream créé précédemment dans le tutoriel. La propriété de balise écoute l’événement price.drop de la couche de données Adobe et mappe les détails du produit concerné en mettant à jour l’élément de données ProductListItems. Une fois les données préparées, une règle dans la propriété de balise se déclenche et envoie l’événement price.drop à AEP via le SDK Web. Cet événement sert ensuite de point d’entrée pour un parcours dans Adobe Journey Optimizer, ce qui permet la diffusion immédiate de notifications push en fonction de la baisse du prix.



