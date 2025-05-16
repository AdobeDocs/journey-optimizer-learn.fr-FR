---
title: Importer des exemples de données CRM dans un jeu de données de profil AEP
description: Importez des exemples d’enregistrements (par exemple, avec CRMID, e-mail, revenu, code postal) pour vérifier si AEP peut correctement assembler ces profils avec des visiteurs web anonymes en fonction d’identifiants partagés tels qu’ECID.
feature: Profiles
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-19T00:00:00Z
jira: KT-18089
source-git-commit: 502cdc41b666959141ff4dfc63608cc463009811
workflow-type: tm+mt
source-wordcount: '291'
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
Ajoutez un champ d’identité **_crmid_** sous l’objet SystemIdentifier . Marquez le champ crmid comme identité et principal.


![profile-schema](assets/finwise-profile-schema.png)

## Préparation des données d’exemple

| crmId | Prénom | Nom | E-mail | loyaltyStatus | annualIncome |
|--------|-----------|----------|---------------------------|---------------|--------------|
| FIN001 | Alice | Wong | alice.wong@example.com | Gold | 336104 |
| FIN002 | Brian | Smith | brian.smith@example.com | Argent | 191065 |
| FIN003 | Cathy | Johnson | cathy.johnson@example.com | Bronze | 117015 |
| FIN004 | David | Lee | david.lee@example.com | Bronze | 61869 |
| FIN005 | Eva | Martinez | eva.martinez@example.com | Argent | 191371 |
| FIN006 | Frank | Marron | frank.brown@example.com | Argent | 196132 |
| FIN007 | Grâce | Kim | grace.kim@example.com | Gold | 309851 |
| FIN008 | Henry | Davis | henry.davis@example.com | Gold | 318378 |
| FIN009 | Isla | Clark | isla.clark@example.com | Argent | 181776 |
| FIN010 | Vérin | Lopez | jack.lopez@example.com | Argent | 186643 |

## Ingestion du fichier CSV

* Créez un jeu de données appelé **_FinWiseCustomerDataSetWithAnnualIncome_** basé sur le **_FinWiseProfileSchema_** créé à l’étape précédente

* Accédez à Connexions -> Sources -> Système local
* Sélectionnez l’option **_Ajouter des données_** sous Chargement de fichier local. Veillez à sélectionner le _**FinWiseCustomerDataSetWithAnnualIncome**_ comme jeu de données cible.
  ![ingest-csv](assets/ingest-csv-into-dataset.png)
* Accédez à l’écran suivant. Chargez le [fichier csv](assets/sample_crm_data.csv) et vérifiez les mappages
  ![mappings](assets/mappings.png)

* Cliquez sur Terminer pour lancer le processus d’ingestion des données

## Vérifier le profil

* Accédez à Client ->Profils et recherchez l’identifiant CRM FinWise égal à FIN001 ou toute autre valeur valide
  ![verify-profile](assets/verify-profiles.png)
