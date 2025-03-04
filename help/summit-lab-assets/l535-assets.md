---
title: Aide-mémoire L535
description: Cette page contient du texte et des liens utilisés dans le L535 Summit Lab.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: 1c3f4341-1293-463d-bee0-57440fcff23a
source-git-commit: 51ab40981a42b0df56d3994f1155eb4ae7575b17
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 21%

---

# Summit Lab L535 - Aide-mémoire

Cette page contient du texte et des liens utilisés dans le L535 Summit Lab. Cela vous permet de copier et coller le contenu dans vos messages Journey Optimizer.

## Liens

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys)
* [Site Web de SecurFinancial](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U)
* [Télécharger l’application](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html)

## Exercices

### Exercice 2.3

**Étape 12** Invite de message électronique :

Générer un e-mail de bienvenue pour le nouveau SecurFinancial
clients qui viennent d’ouvrir un nouveau compte d’épargne. Ajouter un
appel à l&#39;action pour installer l&#39;application mobile SecurFinancial.

### Exercice 3.1

**Étape 7**

```javascript
{%#if select _Push_details1 from profile.pushNotificationDetails where
_Push_details1.token.isNotNull()%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Open the
app
{%else%}
Welcome to your new SecurFinancial checking account! Discover the
SecurFinancial mobile app, designed for effortless banking. Manage accounts,
transfer funds, and monitor transactions securely, anytime, anywhere. Click here
to install the app: https://demo-systemnext.
s3.amazonaws.com/dxdemo/summit/index.html
{%/if%} 
```


![Logo SecureFinancial](/help/summit-lab-assets/assets/SecureFinancial-logo.png)

![Téléphone portable](/help/summit-lab-assets/assets/online-banking-app-01.png)


