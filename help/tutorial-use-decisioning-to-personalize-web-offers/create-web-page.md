---
title: Créer une page web pour tester la solution
description: Page web pour tester les offres personnalisées diffusées à l’aide de la prise de décision.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-05T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-17728
exl-id: 72a67137-303d-4dfe-9b70-322c81e5fb27
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
source-wordcount: '223'
ht-degree: 0%
---
# Créer une page web pour tester la solution

Cette page web a été créée pour tester les offres personnalisées diffusées via Adobe Journey Optimizer Decisioning. Il fournit un environnement contrôlé où l’appel sendEvent peut être déclenché et le contenu d’offre renvoyé affiché, ce qui permet de valider la configuration de personnalisation de bout en bout et de s’assurer que la prise de décision fonctionne comme prévu.

Le script suivant est chargé de récupérer et d’afficher une offre personnalisée sur une page web à l’aide de Adobe Journey Optimizer.

1. Décoder les entités HTML :

   Il existe une fonction d’assistance qui convertit en toute sécurité tous les caractères spéciaux du contenu de l’offre en HTML lisible.

1. Exécutez la personnalisation :

   Lorsqu’elle est appelée, elle envoie une requête (`sendEvent`) à Adobe Web SDK afin d’obtenir du contenu personnalisé pour une zone spécifique de la page (l’élément `#ajo-offer`).

   Si une offre est renvoyée, elle décode l’HTML et l’insère dans la page.

   Si rien n’est renvoyé, un avertissement est consigné.

1. Attendez le SDK :

   Étant donné qu’Adobe SDK (alloy) se charge de manière asynchrone, le script attend qu’il soit complètement chargé avant d’effectuer la requête.

   Il vérifie l’alliage toutes les 200 millisecondes, jusqu’à 20 fois, pour éviter les erreurs.

1. Au chargement de la page :

   Une fois le chargement de la page terminé, le script lance le processus en appelant `waitForAlloy()`.



```javascript
< script >
    function decodeHtmlEntities(html) {
        const txt = document.createElement("textarea");
        txt.innerHTML = html;
        return txt.value;
    }


function runPersonalization() {
    console.log("🚀 Sending personalization request to AJO...");
    alloy("sendEvent", {
        renderDecisions: false,
        personalization: {
            surfaces: ["#ajo-offer"]
        }
    }).then(result => {
        console.log("🔍 Web SDK decision response:", result);

        const decision = result.propositions?.[0];
        const html = decision?.items?.[0]?.data?.content;

        const container = document.getElementById("ajo-offer");
        if (html && container) {
            const decodedHtml = decodeHtmlEntities(html);
            console.log("✅ Offer HTML content (decoded):", decodedHtml);
            container.innerHTML = decodedHtml;
        } else {
            console.warn("⚠️ No personalized offer returned.");
        }


    }).catch(error => {
        console.error("❌ sendEvent failed:", error);
    });
}

function waitForAlloy(callback, retries = 20) {
    if (typeof alloy === "function") {
        callback();
    } else if (retries > 0) {
        console.log("⌛ Waiting for Alloy...");
        setTimeout(() => waitForAlloy(callback, retries - 1), 200);
    } else {
        console.error("❌ alloy is not loaded after waiting.");
    }
}

// Trigger initial personalization on page load
document.addEventListener("DOMContentLoaded", function() {
    waitForAlloy(() => runPersonalization());
}); <
/script>
```

[L’exemple de page HTML et les ressources connexes peuvent être téléchargés ici](assets/web-page-assets.zip)
