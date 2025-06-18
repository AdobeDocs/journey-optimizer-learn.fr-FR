---
title: Diffusion de Personalization avec du contenu JSON dans Adobe Journey Optimizer
description: Tirez parti du type de contenu JSON dans Adobe Journey Optimizer (AJO) pour créer des expériences de personnalisation flexibles et axées sur les données.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-18T00:00:00Z
jira: KT-18387
recommendations: noDisplay, noCatalog
source-git-commit: 9f5b52063605832a9b00c05fb1a93bf60ec7686f
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Diffusion de Personalization avec du contenu JSON dans Adobe Journey Optimizer

Cette section est fournie en tant que ressource supplémentaire pour les utilisateurs expérimentés qui souhaitent mieux contrôler le rendu des offres en front-end.

L’utilisation du type de contenu JSON dans une expérience basée sur du code (CBE) vous permet de renvoyer des données d’offre structurées et de gérer le rendu de manière dynamique à l’aide de JavaScript. Le type de contenu JSON est particulièrement utile pour les scénarios qui nécessitent des mises en page personnalisées, une logique conditionnelle ou l’intégration à des données contextuelles, telles que la météo, l’emplacement ou le type d’appareil.

Bien que cela ne soit pas nécessaire pour la diffusion d’offres de base, cette approche offre une certaine flexibilité aux développeurs qui créent des expériences personnalisées basées sur les données au-delà des fonctionnalités du rendu HTML standard.

## Créez une expérience basée sur le code (CBE) avec le type de contenu JSON.

Commencez par créer une expérience basée sur le code (CBE) dans Adobe Journey Optimizer et définissez le format de contenu sur JSON. Le type de contenu indique à AJO de renvoyer des données d’offre structurées (telles qu’offerText, des images ou des métadonnées) sous la forme d’un objet JSON plutôt que sous la forme d’HTML rendu. Définissez la plateforme (par exemple, Web), l’URL cible où l’offre apparaît et l’emplacement sur la page (par exemple, un ID de conteneur comme offerContainer). Cette configuration permet à votre application web de recevoir des données d’offre et de les rendre dynamiquement à l’aide de JavaScript.

![json-content-type](assets/cbe-json-content.png)

## Associer le CBE à une campagne avec une politique de décision

Une fois l’expérience basée sur le code (CBE) avec le type de contenu JSON créée, elle est liée à une campagne par le biais d’une politique de décision. La politique de décision définit la logique d’éligibilité, de classement et de diffusion de l’offre en fonction du profil ou des données contextuelles.

Lors de l’insertion de la politique de décision dans l’éditeur Personalization (pour les messages in-app ou les e-mails, par exemple), il est important de s’assurer que la sortie conserve une structure JSON valide.

Lorsque vous insérez une politique de décision dans l’éditeur de Personalization (PE) au sein d’une campagne, Adobe Journey Optimizer génère automatiquement une boucle Handlebars en fonction de la politique sélectionnée. Par exemple :
![default-code](assets/handlebar-code-default.png)
Cette boucle effectue une itération sur tous les éléments de décision renvoyés par la politique et injecte le champ offerText de chaque offre. Cette structure par défaut fonctionne bien pour les types de contenu HTML, mais lorsque vous utilisez du contenu JSON, il peut être nécessaire de la restructurer pour produire un tableau ou un objet JSON valide, en particulier si le résultat est analysé par programmation.

![code-restructuré](assets/restructured-code.png)

Ce modèle Handlebars est conçu pour générer un tableau JSON d’objets d’offre, où chaque objet contient un seul champ offerText. Il effectue une boucle sur les éléments de décision renvoyés par la politique de décision spécifiée et enveloppe chaque offerText dans un format d’objet JSON.

## Analyser la réponse d’offre JSON

La réponse d’AJO contient des éléments de décision personnalisés au format JSON sous la structure `propositions[].items[].data.content[]`. Chaque élément de contenu comprend des champs tels que offerText.

```javascript
(response.propositions || []).forEach(p => {
  (p.items || []).forEach(item => {
    const contents = item.data?.content || [];
    contents.forEach(contentItem => {
      const html = contentItem.offerText || "";
      const wrapper = document.createElement("div");
      wrapper.className = "offer";
      wrapper.innerHTML = html;
      document.getElementById("offerContainer").appendChild(wrapper);
    });
  });
});
```

### Exemples de ressources

Pour vous aider à commencer, téléchargez l’exemple de fichier HTML et de fichier JavaScript qui montrent comment utiliser des offres basées sur JSON et les générer dynamiquement sur votre page web.

[Code JavaScript](assets/weather-related-offers-script-multiple-json.js)
[Fichier HTML](assets/multiple-json.html)