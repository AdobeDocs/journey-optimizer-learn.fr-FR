---
title: Création d’audiences dans Adobe Journey Optimizer
description: Découvrez comment définir et créer des audiences ciblées dans AJO pour alimenter des parcours clients personnalisés et une prise de décision en temps réel
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
jira: KT-17923
exl-id: d90f1868-0514-49b2-832d-82460883b6e4
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%
---
# Création d’audiences dans Adobe Journey Optimizer


Dans Adobe Experience Platform, les audiences sont des groupes d’utilisateurs créés en fonction de leurs actions, préférences ou informations de profil, afin de proposer des expériences personnalisées.

* Connexion à Journey Optimizer
* Accédez à Client -> Audiences ->Créer une audience
* Création d’audiences à l’aide de la méthode Créer une règle

  ![audience](assets/rule-based-audience.png)

* Créez les 3 audiences suivantes

  * Clients intéressés par les actions

  * Clients intéressés par les obligations

  * Clients intéressés par le CD


* Assurez-vous que la méthode d’évaluation de chaque audience est définie sur _****_ pour la qualification en temps réel.
  ![edge-audience](assets/audience-edge.png)

* Utilisez le champ Instrument financier préféré pour segmenter les utilisateurs en fonction de leur intérêt d’investissement sélectionné, tel que Actions, Obligations ou CD

![event](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>>Si le champ PreferredFinancialInstrument n’est pas visible dans l’onglet Événements, cliquez sur l’icône des paramètres et activez/désactivez l’option Afficher l’ensemble du schéma XDM.



![toggle-full-xdm-schema](assets/show-custom-fields.png)
