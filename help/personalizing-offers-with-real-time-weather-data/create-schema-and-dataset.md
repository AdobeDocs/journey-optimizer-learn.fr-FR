---
title: Configurer un schéma, un jeu de données et un flux de données XDM dans AEP
description: Création d’un schéma, d’un jeu de données et d’un flux de données XDM
feature: Audiences
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-06-10T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
source-git-commit: dac6b373226bd0be2533cf859e4f250018cf568b
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Configurer un schéma, un jeu de données et un flux de données XDM dans AEP

## Créer un schéma XDM

Pour utiliser Adobe Experience Platform Web SDK (Alloy.js) sur une page web, les balises AEP doivent être associées à un flux de données mappé à un schéma d’événement XDM. Le SDK Web (alloy.sendEvent) envoie des données dans AEP en tant qu’événements d’expérience, qui doivent être conformes à un schéma XDM basé sur la classe XDM ExperienceEvent .

Pour créer un schéma XDM

* Connexion à Adobe Experience Platform
* Gestion des données -> Schémas -> Créer un schéma

* Créez un schéma basé sur un événement XDM appelé **_Weather-Schema_**. Si vous ne connaissez pas la création d’un schéma, consultez cette [documentation](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/tutorials/create-schema-ui)


* Assurez-vous que le schéma comporte les champs suivants avec le type de données approprié.

![schéma-météo](assets/weather-schema.png)

## Création d’un jeu de données basé sur le schéma

Un **jeu de données dans Adobe Experience Platform (AEP)** est un conteneur de stockage structuré utilisé pour ingérer, stocker et activer des données en fonction d’un schéma XDM défini.


* Gestion des données -> Jeux de données -> Créer un jeu de données
* Créez un jeu de données appelé **_Weather-schema-dataset_** basé sur le schéma XDM (_&#x200B;**Weather-Schema**&#x200B;_) créé à l’étape précédente.


## Créer un flux de données

Un flux de données dans Adobe Experience Platform est comme un pipeline (ou une autoroute) sécurisé qui connecte votre site web ou votre application aux services Adobe, permettant aux données d’entrer et au contenu personnalisé de revenir.

* Accédez à Collecte de données > Flux de données, puis cliquez sur Nouveau flux de données. Nommez le flux de données **weather-related-datastream**


* Fournissez les détails suivants, comme illustré dans la capture d’écran ci-dessous.
  ![flux de données](assets/datastream.png)
* Cliquez sur Enregistrer , puis sur Ajouter un mappage et ajoutez le service Adobe Experience Platform et le jeu de données d’événement avec les cases à cocher appropriées sélectionnées
  ![datastream-mapping](assets/datastream-service.png)

* Enregistrez le flux de données.
