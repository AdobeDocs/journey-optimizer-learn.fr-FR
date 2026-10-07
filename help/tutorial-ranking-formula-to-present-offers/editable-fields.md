---
title: Utilisation de champs de formulaire modifiables dans les expériences basées sur du code AJO
description: Découvrez comment créer des blocs de contenu modifiables à l’aide de champs de formulaire intégrés dans les modèles d’expérience basée sur du code Adobe Journey Optimizer afin d’offrir aux personnes spécialisées dans le marketing un contenu de campagne dynamique et réutilisable.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-22T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18416
exl-id: 0ba695d6-becb-440d-b0d0-de5b51b42562
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
source-wordcount: '221'
ht-degree: 22%
---
# Utilisation de champs de formulaire modifiables dans les expériences basées sur du code AJO

Dans de nombreux parcours marketing, en particulier dans les industries réglementées, il est essentiel d&#39;inclure une clause de non-responsabilité qui peut varier en fonction de la campagne, de la zone géographique ou du produit. En utilisant un [champ modifiable](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/channels/code-based-experience-channel/form-fields-in-code-based-experiences) directement dans l’éditeur Personalization d’AJO, les spécialistes marketing et les équipes juridiques peuvent conserver un contrôle total sur le texte de clause de non-responsabilité sans impliquer les développeurs ni modifier la logique de décision.

Cela permet des mises à jour rapides et garantit la conformité entre les campagnes tout en exploitant le contenu décisionnel tel que les offres.

## Insérer un champ modifiable dans l’éditeur de personnalisation

- Ouvrez la campagne créée à l’étape précédente.
- Cliquez sur _**Modifier la campagne**_
- Accédez à l’onglet _**Contenu**_
- Cliquez sur _**Modifier le code**_ et insérez un champ modifiable appelé legalDisclaimer avec une valeur par défaut en utilisant la syntaxe suivante dans l’éditeur de personnalisation

- `{{#inline "legalDisclaimer" name="Legal Disclaimer"}} Legal Disclaimer will go here {{/inline}}`

- Utilisez la variable `{{{legalDisclaimer}}}` dans le modèle, comme illustré ci-dessous

- ![champs-modifiables](assets/editable-fields.png)

- Les marketeurs peuvent facilement modifier le champ Clause de non-responsabilité sans avoir à ouvrir l&#39;éditeur de personnalisation.
- ![marketeur-champ-modifiable](assets/editable-field-marketer-view.png)



## Publier la campagne

Activez la campagne pour commencer à diffuser des offres personnalisées en temps réel.
