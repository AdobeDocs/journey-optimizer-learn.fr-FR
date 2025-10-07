---
title: Importer des exemples de données CRM dans un jeu de données de profil AEP
description: Importez des exemples d’enregistrements (par exemple, avec CRMID, e-mail, revenu, code postal) pour vérifier si AEP peut correctement assembler ces profils avec des visiteurs web anonymes en fonction d’identifiants partagés tels qu’ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18089
exl-id: 33c8c386-f417-45a8-83cf-7312d415b47a
source-git-commit: 83b23f54594b796ec528526a360c5c40164fb5cb
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 6%

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
Ajoutez le groupe de champs _**Détails des consentements et des préférences**_ au schéma. [Consentements et préférences](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/profile/consents) est un groupe de champs standard pour la classe XDM Individual Profile qui recueille les informations de consentement et de préférence pour un client individuel. Les préférences stockées ici déterminent les préférences de communication au niveau du canal.


![profile-schema](assets/finwise-profile-schema.png)

## Préparation des données d’exemple

Mettez à jour les adresses e-mail factices vers des adresses réelles. Ils seront utilisés ultérieurement lors de l’envoi de messages avec Adobe Journey Optimizer. Définissez emailConsent sur y pour activer la diffusion par e-mail pour les profils.

|   | crmId | Prénom | Nom | e-mail | loyaltyStatus | zipCode | annualIncome | emailConsent |
|---|--------|-----------|----------|-------------------------|---------------|---------|--------------|--------------|
|   | FIN001 | Alice | Wong | alice.wong@example.com | Gold | 92128 | 120000 | y |
|   | FIN002 | Bob | Smith | bob.smith@example.com | Argent | 92126 | 85000 | y |
|   | FIN003 | Charlie | Kim | charlie.kim@example.com | Platine | 60614 | 175000 | y |
|   | FIN004 | Diana | Lee | diana.lee@example.com | Gold | 30303 | 98000 | y |
|   | FIN005 | Ethan | Marron | ethan.brown@example.com | Bronze | 75201 | 60000 | y |

## Ingestion du fichier CSV

* Créez un jeu de données appelé **_FinWiseCustomerDataSetWithAnnualIncome_** basé sur le **_FinWiseProfileSchema_** créé à l’étape précédente

* Accédez à Connexions -> Sources -> Système local
* Sélectionnez l’option **_Ajouter des données_** sous Chargement de fichier local. Veillez à sélectionner le _**FinWiseCustomerDataSetWithAnnualIncome**_ comme jeu de données cible.
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* Accédez à l’écran suivant. Chargez le [fichier csv](assets/finwise_profiles.csv) et vérifiez les mappages
  ![mappings](assets/mappings.png)

* Cliquez sur Terminer pour lancer le processus d’ingestion des données

## Vérifier le profil

* Accédez à Client ->Profils et recherchez l’identifiant CRM FinWise égal à FIN001 ou toute autre valeur valide
  ![verify-profile](assets/verify-profiles.png)
