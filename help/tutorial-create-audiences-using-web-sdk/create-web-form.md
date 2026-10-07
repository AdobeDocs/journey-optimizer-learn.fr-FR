---
title: Création d’un formulaire web
description: Créez un formulaire dans votre page HTML qui permet aux utilisateurs de sélectionner leurs préférences d’investissement
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-04-30T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17923
exl-id: 20de8dec-aac8-43ed-8305-e723f82a5dd9
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
source-wordcount: '125'
ht-degree: 0%
---
# Création d’un formulaire web

Le formulaire HTML suivant a été créé pour capturer la préférence des utilisateurs
![html-form](assets/web-form.png)

Lorsqu’un utilisateur clique sur le bouton de la page web, ses préférences financières sélectionnées (telles que les actions, les obligations ou les CD) sont capturées et intégrées à la couche de données d’Adobe. Cet événement (assetClassSelection) stocke le choix de l’utilisateur en temps réel. Adobe Launch écoute ensuite cet événement, récupère l’option d’investissement sélectionnée (PreferredFinancialInstrument) et peut déclencher des actions telles que l’envoi des données à Adobe Experience Platform (AEP) ou la mise à jour des règles de personnalisation

Le code JavaScript suivant a été écrit pour gérer l’envoi du formulaire

```javascript
function handleSubmission() {
  window.adobeDataLayer = window.adobeDataLayer || [];

  const selectedAssetClass = document.querySelector('input[name="assetclass"]:checked');
  const errorMessage = document.getElementById("error-message");
  const messageBox = document.getElementById("message");

  if (!selectedAssetClass) {
    errorMessage.textContent = "Please select a financial instrument.";
    messageBox.textContent = "";
    return;
  }

  errorMessage.textContent = "";

  const subscriptionEvent = {
    event: "assetClassSelection",
    xdm: {
      eventType: "assetClassSelection",
      eventID: "investment_preference_event",
      timestamp: new Date().toISOString(),
      FinancialInterest: {
        PreferredFinancialInstrument: selectedAssetClass.value
      }
    }
  };

  console.log("📩 Sending asset class data to AEP:", subscriptionEvent);
  window.adobeDataLayer.push(subscriptionEvent);

  // ✅ Show thank-you message
  messageBox.textContent = `Thank you for selecting "${selectedAssetClass.value}". We'll use this to personalize your experience.`;
}
```

[L’exemple de formulaire HTML est fourni dans le cadre de ce tutoriel](assets/webform.zip)
