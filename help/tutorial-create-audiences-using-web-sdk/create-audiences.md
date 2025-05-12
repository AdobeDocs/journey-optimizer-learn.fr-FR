---
title: Création d’audiences dans Adobe Journey Optimizer
description: Découvrez comment définir et créer des audiences ciblées dans AJO pour alimenter des parcours clients personnalisés et une prise de décision en temps réel
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00Z
jira: KT-17923
source-git-commit: ba83be3caf214d2daaa8c99556d246686ff3f0cb
workflow-type: tm+mt
source-wordcount: '148'
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


* Assurez-vous que la méthode d’évaluation de chaque audience est définie sur _&#x200B;**Edge**&#x200B;_ pour la qualification en temps réel.
  ![edge-audience](assets/audience-edge.png)

* Utilisez le champ Instrument financier préféré pour segmenter les utilisateurs en fonction de leur intérêt d’investissement sélectionné, tel que Actions, Obligations ou CD

![event](assets/event-attribute.png)

![PreferredFinancialInstrument](assets/stock-customers.png)




>[!NOTE]
>
>&#x200B;>Si le champ PreferredFinancialInstrument n’est pas visible dans l’onglet Événements, cliquez sur l’icône des paramètres et activez/désactivez l’option Afficher l’ensemble du schéma XDM.



![toggle-full-xdm-schema](assets/show-custom-fields.png)


