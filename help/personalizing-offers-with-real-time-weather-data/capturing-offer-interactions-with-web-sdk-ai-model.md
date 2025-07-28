---
title: Capturer les interactions d’offres avec Adobe Web SDK pour la formation des modèles d’IA
description: Cet article fournit des conseils sur la capture de données d’interaction utilisateur, telles que les impressions d’offre et les clics, à l’aide de Adobe Experience Platform Web SDK (alloy.js). Ces données servent de base pour l’entraînement intelligent des modèles d’IA dans Adobe Journey Optimizer (AJO) afin de classer les offres en fonction du comportement des utilisateurs et des utilisatrices et des signaux contextuels.
feature: Decisioning
topic: Integrations
role: User
level: Beginner
doc-type: Article
last-substantial-update: 2025-07-08T00:00:00Z
jira: KT-18451
exl-id: 3cb280b3-71e5-4e91-9252-5679d794d4c4
source-git-commit: 6c4f33d1f55be298781cfb0958862f9710e3647a
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 4%

---

# Capturer les interactions d’offres avec Adobe Web SDK pour la formation des modèles d’IA

>[!NOTE]
>
> Ne terminez cet article que si vous prévoyez d’utiliser des méthodes de classement basées sur l’IA dans Adobe Journey Optimizer pour personnaliser l’offre affichée en fonction de l’engagement prévu.



Cet article explique comment capturer des événements d’interaction d’offre (tels que des impressions ou des clics) à l’aide de Adobe Experience Platform Web SDK en appelant alloy(« sendEvent, » ...) directement dans votre code JavaScript. Les données sont ingérées dans AEP et utilisées pour entraîner des modèles d’IA dans Adobe Journey Optimizer (AJO) en vue d’un classement d’offres plus intelligent basé sur le comportement en temps réel.

Pour créer un modèle d&#39;IA pour le classement des offres dans Adobe Journey Optimizer, votre jeu de données doit être basé sur un schéma qui inclut le groupe de champs Interactions de proposition . Ce groupe de champs prend en charge des événements de prise de décision clés tels que decisioning.propositionDisplay et decisioning.propositionInteract, ainsi que les champs requis tels que occupeedPropositions, display et interaction.

Il existe deux approches valides pour y parvenir :

- Créez un schéma, un jeu de données et un flux de données configurés spécifiquement pour le suivi des interactions
- Mettre à jour un schéma existant - ce qui est fait dans ce tutoriel



## Mettre à jour le schéma existant pour capturer les événements d’interaction d’offre

Au lieu de créer un schéma, le schéma d’événement d’expérience existant utilisé pour les offres liées à la météo est mis à jour pour prendre en charge le suivi des interactions.

Dans Adobe Experience Platform :

- Ouvrez le schéma d’événement d’expérience _&#x200B;**Weather-Schema**&#x200B;_ existant que vous utilisez pour les offres basées sur la météo.

- Ajoutez le groupe de champs :
Événement d’expérience - Interactions de propositions

Vous n’avez pas besoin de créer un nouveau jeu de données ou flux de données — continuez à utiliser votre configuration existante pour les offres météorologiques. Les événements envoyés correspondent aux attentes de Adobe Journey Optimizer en matière de formation des modèles d’IA et de suivi des performances des offres.


Continuer à utiliser le jeu de données actuel (pas besoin d’en créer un nouveau)

Le flux de données existant est déjà configuré et utilisé dans la propriété Adobe Experience Platform Tags ; aucune modification n’est nécessaire à cet endroit.

Web SDK achemine automatiquement les nouveaux événements d’interaction vers la destination correcte.

Cette configuration rationalisée garantit que tous les événements météorologiques et de prise de décision sont ingérés dans un seul jeu de données unifié, ce qui est idéal pour entraîner des modèles d’IA dans Adobe Journey Optimizer.


## Capturer Des Événements D’Affichage D’Offre (Impressions)

La structure HTML de l’offre a été modifiée pour inclure des éléments interactifs (en particulier des balises `<a>` et `<button>`) permettant aux utilisateurs et utilisatrices d’interagir avec l’offre (par exemple, les boutons « Demander l’offre » ou « En savoir plus »).

Chaque bouton comprend un attribut data-offer-id afin que l’interaction correspondante puisse être correctement suivie.



Pour consigner le moment où les offres sont présentées aux utilisateurs, le fichier JavaScript existant utilisé pour le rendu des offres météorologiques a été mis à jour afin d’inclure le suivi des événements d’affichage.

Un événement decisioning.propositionDisplay est désormais envoyé à l&#39;aide du SDK Web Adobe (alloy.sendEvent) lorsqu&#39;une ou plusieurs offres sont affichées. Cet événement inclut l’affichage requis : 1 indicateur et fait référence aux propositions impliquées.


```javascript
alloy("sendEvent", {
                    xdm: {
                      _id: generateUUID(),
                      timestamp: new Date().toISOString(),
                      eventType: "decisioning.propositionInteract",
                      identityMap: {
                        ECID: [{
                          id: ecidValue,
                          authenticatedState: "ambiguous",
                          primary: true
                        }]
                      },
                      _experience: {
                        decisioning: {
                          propositionEventType: {
                            interact: 1
                          },
                          propositionAction: {
                            id: offerId,
                            tokens: [trackingToken]
                          },
                          propositions: window.latestPropositions
                        }
                      }
                    }
                  });
```

## Capturer Des Événements De Clic D’Offre (Interactions)

Pour suivre le moment où un utilisateur clique sur une offre, nous avons mis à jour le JavaScript existant afin d’écouter les clics sur les éléments `<a>` et `<button>` rendus dans le conteneur d’offres.

Lorsqu&#39;un clic est détecté, un événement decisioning.propositionInteract est envoyé à l&#39;aide du SDK Web Adobe. L’événement inclut l’interaction nécessaire : 1 indicateur et fait référence à l’ID d’offre et à la portée de décision spécifiques.

```javascript
// Attach click tracking to <a> and <button> elements
child.querySelectorAll("a, button").forEach(el => {
                el.addEventListener("click", () => {
                  const ecidValue = getECID();
                  if (!ecidValue || !offerId || !trackingToken) {
                    console.warn("Girish!!!!  Missing ECID, offerId, or trackingToken. Interaction event not sent.");
                    return;
                  }

                  alloy("sendEvent", {
                    xdm: {
                      _id: generateUUID(),
                      timestamp: new Date().toISOString(),
                      eventType: "decisioning.propositionInteract",
                      identityMap: {
                        ECID: [{
                          id: ecidValue,
                          authenticatedState: "ambiguous",
                          primary: true
                        }]
                      },
                      _experience: {
                        decisioning: {
                          propositionEventType: {
                            interact: 1
                          },
                          propositionAction: {
                            id: offerId,
                            tokens: [trackingToken]
                          },
                          propositions: window.latestPropositions
                        }
                      }
                    }
                  });
                });
              });
```

## Création d’un modèle d’IA pour le classement des offres dans Adobe Journey Optimizer Offer Decisioning

Grâce à, les impressions d’offres et les clics sont désormais capturés via le Web SDK et stockés dans Adobe Experience Platform. Ces données peuvent être utilisées pour entraîner un modèle d’IA qui prédit les offres les plus susceptibles de stimuler l’engagement.

Ce modèle d’IA est référencé dans une formule de classement ou une stratégie de sélection afin de déterminer les offres prioritaires pour chaque utilisateur.
- Connexion à Journey Optimizer
- Accédez à Prise de décision -> Configuration de la stratégie -> Modèles d’IA ->Créer un modèle d’IA.
- Veillez à utiliser le jeu de données correct
  ![ai-model](assets/ai-model.png)
- Enregistrez et activez le modèle d’IA.
- Mettez à jour la stratégie de sélection créée à l’étape précédente pour utiliser le modèle d’IA pour la méthode de classement .
  ![update-selection-strategy](assets/update-selection-strategy.png)

## Tester la solution

Incluez le [fichier JavaScript mis à jour](assets/ai-model.js) dans la [page web existante](assets/weather-offers.html)
