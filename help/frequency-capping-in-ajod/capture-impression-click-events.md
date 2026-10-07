---
title: Capturer des événements d’impressions et d’interactions
description: Capturez les événements d’impression et d’interaction et préparez les données pour le compte rendu des performances dans Journey Optimizer.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
recommendations: noDisplay, noCatalog
last-substantial-update: 2025-07-18T00:00:00.000Z
jira: KT-18526
exl-id: 7e6014b5-c5a6-467b-8e31-58c5d966464c
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
source-wordcount: '472'
ht-degree: 12%
---
# Capturer des événements d’impressions et d’interactions

Pour activer le reporting sur les impressions d&#39;offre et les clics provenant d&#39;AJO Decisioning, les composants suivants doivent être configurés :
>[!NOTE]
>
> Ces conditions préalables ont déjà été remplies dans la section Créer un schéma et un jeu de données du [tutoriel précédent](https://experienceleague.adobe.com/en/docs/journey-optimizer-learn/personalizing-offers-with-real-time-weather-data/create-schema-and-dataset)

## &#x200B;1. Jeu de données dans Adobe Experience Platform (AEP)

- Jeu de données basé sur un schéma **XDM ExperienceEvent**.

Le schéma doit inclure `Web Details` groupe de champs qui capture l’URL de la page, le référent, etc.

## &#x200B;2. Configuration du flux de données

- Un **flux de données** doit être créé dans Adobe Experience Platform.
- Ce flux de données doit être lié au jeu de données configuré ci-dessus pour s’assurer que tous les événements Web SDK sont correctement ingérés dans la bonne destination.

## &#x200B;3. Propriété Adobe Experience Platform Tags

- Extension AEP Web SDK configurée pour utiliser le flux de données créé à l’étape précédente.
- Service Experience Cloud ID configuré
- Un élément de données appelé ECID est ajouté à la propriété
- Implémenté sur le site où les offres sont rendues.


Pour activer le reporting sur les performances des offres, la première étape consiste à capturer le moment où les offres sont affichées (impressions) et celui où les visiteurs les cliquent (interactions). Ces événements fournissent la base nécessaire pour mesurer l’engagement, calculer les taux de clics publicitaires et analyser l’efficacité des offres dans Adobe Experience Platform.

La fonction alloy(« sendEvent ») est utilisée pour consigner les interactions utilisateur avec les offres renvoyées par Adobe Journey Optimizer (AJO).

La payload sendEvent capture les interactions d’offre en incluant le type d’événement (decisioning.propositionDisplay pour les impressions ou decisioning.propositionInteract pour les clics), un identifiant d’événement unique, l’horodatage et l’identité de l’utilisateur (identityMap). Elle inclut également la liste des offres (propositions) affichées ou sur lesquelles l’utilisateur ou l’utilisatrice a cliqué, ainsi que des jetons de suivi pour garantir une attribution précise. Cette structure permet le reporting et l’optimisation des performances des offres personnalisées dans Adobe Journey Optimizer.

Deux types d’événements d’interaction sont capturés :

## Événement d’impression

Une impression se produit lorsqu’une offre est rendue sur la page et devient visible par l’utilisateur. Le suivi de l&#39;événement s&#39;effectue à l&#39;aide du type d&#39;événement decisioning.propositionDisplay.


```javascript
 alloy("sendEvent", {
            xdm: {
              _id: generateUUID(),
              timestamp: new Date().toISOString(),
              eventType: "decisioning.propositionDisplay",
              identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
                      authenticatedState: "authenticated",
                      primary: true
                    }]
                  },
              _experience: {
                decisioning: {
                  propositionEventType: {
                    display: 1
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
        }
```

## Interaction d’offre

Une interaction est enregistrée lorsqu’un utilisateur clique sur un call-to-action (CTA) dans l’offre rendue. Le suivi de l&#39;événement s&#39;effectue à l&#39;aide du type d&#39;événement decisioning.propositionInteract.

```javascript
alloy("sendEvent", {
                xdm: {
                  _id: generateUUID(),
                  timestamp: new Date().toISOString(),
                  eventType: "decisioning.propositionInteract",
                  identityMap: {
                    ECID: [{
                      id: _satellite.getVar("ECID"),
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
              })
```

L’inclusion de propositions dans les événements de clics et d’impressions est essentielle pour un reporting précis des offres dans Adobe Journey Optimizer. Ces propositions représentent les offres exactes qui ont été présentées à l’utilisateur ou l’utilisatrice, ce qui permet à Adobe d’attribuer les interactions utilisateur (par exemple, les impressions ou les clics) aux décisions spécifiques prises par le système.

Chaque offre dans une proposition comprend un jeton de suivi, qui est un identifiant unique généré par Adobe. Ce jeton doit être transmis exactement tel qu’il est reçu, sans modification, dans l’événement de clic ou d’impression correspondant. Les jetons de suivi correspondants permettent à Adobe d’associer précisément l’action de l’utilisateur ou utilisatrice à la décision d’offres correcte, ce qui active la création de rapports en aval et l’optimisation basée sur l’IA.
