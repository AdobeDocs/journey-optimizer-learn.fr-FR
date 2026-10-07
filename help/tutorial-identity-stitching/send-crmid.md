---
title: Créer l’exemple d’application pour simuler l’activité de connexion
description: Créez un exemple d’application Node.js pour simuler un flux de connexion
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: e080149c-0ac0-4559-b99d-ebad9f03b98b
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
source-wordcount: '208'
ht-degree: 0%
---
# Créer l’exemple d’application pour simuler l’activité de connexion

Cet exemple d’application, créé et déployé sur un serveur Node.js, montre comment envoyer un identifiant CRM à Adobe Experience Platform (AEP) lorsqu’un utilisateur se connecte. L’application simule un flux de connexion dans lequel les informations d’identification de l’utilisateur sont validées côté serveur. Une fois la connexion établie, l’identifiant CRM de l’utilisateur est récupéré et envoyé à adobeDataLayer, ce qui déclenche une règle correspondante dans Adobe Experience Platform Tags (anciennement Adobe Launch).

La fonction attachmentLoginHandler associe un écouteur d’événement d’envoi à un formulaire de connexion. Lors de l’envoi du formulaire, il empêche l’action par défaut, valide les informations d’identification par rapport à l’objet d’un utilisateur prédéfini et récupère l’identifiant CRM si celui-ci est valide. La fonction transmet un événement enregistré par l’utilisateur avec l’identifiant CRM et l’état d’authentification à adobeDataLayer, puis Adobe Experience Platform Tags le sélectionne pour envoyer les données à Adobe Experience Platform (AEP).


```javascript
function attachLoginHandler() {
    const form = document.getElementById("loginForm");
    if (!form) return;

    form.addEventListener("submit", function(e) {
        e.preventDefault();
        const username = document.getElementById("username").value;
        const password = document.getElementById("password").value;

        if (users[username] && users[username].password === password) {
            const crmid = users[username].crmid;
            window.adobeDataLayer = window.adobeDataLayer || [];
            debugger;
            window.adobeDataLayer.push({
                event: "UserLoggedIn",
                user: {
                    crmid: crmid,
                    authenticatedState: "authenticated"
                }
            });
        }
    });
}
```

Le script des balises Adobe Experience Platform est inclus dans la section `<head>` de la page HTML à l’aide d’une balise `<script>`, généralement comme suit :

`<script src="https://assets.adobedtm.com/b5eu4857867/4e4d84957/launch-b69e276bb9b5-development.min.js" async crossorigin="anonymous"></script>`

Le script AEP Tags a été obtenu en publiant une propriété compatible avec Web SDK créée à l’étape précédente et en copiant le code incorporé à partir de l’onglet Environnements .
