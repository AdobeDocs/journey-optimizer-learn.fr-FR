---
title: Création d’une politique de décision
description: Utilisez une politique de décision pour définir la logique afin de déterminer les offres diffusées à un utilisateur ou une utilisatrice lors de la personnalisation.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: 186e4a7d-6077-401f-9958-2f955214bc35
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
source-wordcount: '246'
ht-degree: 8%
---
# Créer une politique de décision

Les politiques de décision sont des conteneurs pour vos offres qui s’appuient sur le moteur [!UICONTROL Decisioning] afin de sélectionner le meilleur contenu à diffuser en fonction de l’audience.

1. Dans l’éditeur de personnalisation, cliquez sur l’élément **[!UICONTROL Politique de décision]** dans le volet de navigation de gauche, puis cliquez sur **[!UICONTROL Ajouter une politique de décision]**.

   ![create-decision-policy](assets/decision-policy.png)

1. Cliquez sur **[!UICONTROL Ajouter]** pour sélectionner la stratégie de sélection.

   ![politique-décision](assets/decision-policy2.png)

1. Cliquez sur **[!UICONTROL Sélectionner une offre de secours]** pour sélectionner l’offre de secours.
1. Cliquez sur **[!UICONTROL Suivant]** pour passer en revue la politique de décision.
1. Cliquez sur **[!UICONTROL Créer]** pour terminer le processus de création de la politique de décision.

## Utilisation de la politique de décision dans l’éditeur de code

1. Dans l’éditeur de personnalisation, cliquez sur **[!UICONTROL Insérer une politique]**.

   Le code correspondant à la politique de décision est ajouté.

   À ce stade, vous pouvez inclure tous les attributs de décision requis directement dans le code. Ces attributs sont définis dans le schéma utilisé par le catalogue d&#39;offres. Les attributs standard sont organisés sous l’espace de noms `__experience`, tandis que les attributs personnalisés spécifiques à votre organisation sont stockés sous l’espace de noms `_<imsOrg>`.

   ![using_decision_policy](assets/Insert-policy.png)

   Ce code parcourt une liste d’offres personnalisées choisies pour l’utilisateur et affiche le texte de chacune d’elles sur la page web. Il affiche le message (appelé `offerText`) de chaque offre dans un paragraphe, afin que les utilisateurs puissent voir clairement leur contenu personnalisé.

   Si aucune offre personnalisée n&#39;est disponible, une offre de secours s&#39;affiche pour vous assurer que l&#39;espace n&#39;est pas laissé vide.

1. Cliquez sur **[!UICONTROL Enregistrer]**, puis activez la campagne.
