---
title: Envoyer le CRMID à Adobe Experience Platform
description: Création de balises Adobe Experience Platform pour envoyer le CRMID reçu du navigateur à Adobe Experience Platform
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 894ad6b7-c4b4-465e-8535-3fdcd77e00eb
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
    internal-label: Journey Optimizer
feature_v2:
  - id: d2971708-e780-44bb-9e2a-72f139796afd
    internal-label: Customer
subfeature_v2:
  - id: ef9a83ca-eefa-47cf-aa34-f1a34715583a
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: d4f3ee0d644b4f962763e6807f014efe132a9a05
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 10%
---
# Envoyer le CRMID à Adobe Experience Platform

Adobe Experience Platform Tags est utilisé pour envoyer le CRMID à Adobe Experience Platform (AEP), car il fournit un mécanisme flexible piloté par les événements pour transmettre des données d’identité directement depuis le navigateur. L’envoi d’un CRMID après la connexion de l’utilisateur permet à AEP de lier l’ECID anonyme au profil CRM connu, ce qui permet un regroupement précis des identités. Ce lien constitue la base de la création de profils clients unifiés, de la qualification des audiences et de la diffusion d’expériences personnalisées en temps réel dans Adobe Journey Optimizer (AJO).

Une propriété Experience Platform Tags appelée _**FinWise**_ est créée. Les extensions suivantes ont été ajoutées à la propriété Tags

![tags-extensions](assets/tags-extensions.png)

Configurez l’extension AEP Web SDK à l’aide du flux de données Financial Advisors créé à l’étape précédente.
Le service Experience Cloud ID est une extension facultative ajoutée à la propriété de balise à des fins de débogage.

## Balisage des éléments de données

Créez les éléments de données suivants

| Élément de données | Extension | Type d’élément de données | Paramètres personnalisés |
|--------------|-----------------------------------|---------------------------|----------------------------------------|
| crmid | Couche de données client Adobe | État calculé de la couche de données | user.crmid |
| ECID | Service Experience Cloud ID | ECID |                                        |
| une identité | SDK web Adobe Experience Platform | Mappage d’identités | ![Image](assets/identity-settings.png) |
| Variable XDM | SDK web Adobe Experience Platform | Variable | ![Image](assets/xdmvariable.png) |

## Créer une règle

Créez une règle appelée LoginEvent avec l’événement et les actions suivants :

Événement
![event](assets/data-pushed-event1.png)

Action Mettre à jour la variable
![update-variable](assets/update-variable1.png)
Action Envoyer l’événement
![send-event](assets/send-event1.png)

## Enregistrer et créer

Enregistrez vos modifications, créez et créez la bibliothèque.
