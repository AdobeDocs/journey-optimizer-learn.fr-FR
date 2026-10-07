---
title: Importer des exemples de données CRM dans un jeu de données de profil AEP
description: Importez des exemples d’enregistrements (par exemple, avec CRMID, e-mail, revenu, code postal) pour vérifier si AEP peut correctement assembler ces profils avec des visiteurs web anonymes en fonction d’identifiants partagés tels qu’ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00.000Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
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
source-wordcount: '305'
ht-degree: 5%
---
# Importer des exemples de données CRM dans un jeu de données de profil AEP

Pour commencer la combinaison d’identités, importez des exemples de données de profil CRM dans un jeu de données lié à un schéma activé pour les profils dans Adobe Experience Platform

## Création d’un espace de noms personnalisé

* Accédez à Client -> Identités -> Créer un espace de noms d’identité.
* Sélectionnez Identifiant individuel sur l’ensemble des appareils et indiquez le nom d’affichage et le symbole d’identité, comme illustré dans la capture d’écran ci-dessous.
  ![espace-de-noms-personnalisé](assets/custom-namespace.png)

## Création d’un schéma activé pour le profil

Créez un schéma de profil individuel appelé **_FinWiseProfileSchema_**. Incluez des champs tels que annualIncome, email, firstName, lastName et loyaltyStatus.
Ajoutez un champ d&#39;identité **_crmid_** comme illustré. Marquez le champ crmid comme identité et principal.


![profile-schema](assets/finwise-profile-schema.png)

## Préparation des données d’exemple

Mettez à jour les adresses e-mail factices vers des adresses réelles. Ils seront utilisés ultérieurement lors de l’envoi de messages avec Adobe Journey Optimizer.

|   | crmId | Prénom | Nom | E-mail | loyaltyStatus | zipCode | annualIncome |
|---|--------|-----------|----------|-------------------------|---------------|---------|--------------|
|   | FIN001 | Alice | Wong | alice.wong@example.com | Gold | 92128 | 120000 |
|   | FIN002 | Bob | Smith | bob.smith@example.com | Argent | 92126 | 85000 |
|   | FIN003 | Charlie | Kim | charlie.kim@example.com | Platine | 60614 | 175000 |
|   | FIN004 | Diana | Lee | diana.lee@example.com | Gold | 30303 | 98000 |
|   | FIN005 | Ethan | Marron | ethan.brown@example.com | Bronze | 75201 | 60000 |

## Ingestion du fichier CSV

* Créez un jeu de données appelé **_FinWiseCustomerDataSetWithAnnualIncome_** basé sur le **_FinWiseProfileSchema_** créé dans l’exemple précédent. Assurez-vous que le jeu de données est activé pour le profil.

* Accédez à Connexions -> Sources -> Système local
* Sélectionnez l’option **_Ajouter des données_** sous Chargement de fichier local. Veillez à sélectionner le _&#x200B;**FinWiseCustomerDataSetWithAnnualIncome**&#x200B;_ comme jeu de données cible.
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* Accédez à l’écran suivant. Chargez le [fichier csv](assets/finwise_profiles.csv) et vérifiez les mappages
  ![mappings](assets/mappings.png)

* Cliquez sur Terminer pour lancer le processus d’ingestion des données

## Vérifier le profil

* Accédez à Client ->Profils et recherchez l’identifiant CRM FinWise égal à FIN001 ou toute autre valeur valide
  ![verify-profile](assets/verify-profiles.png)
