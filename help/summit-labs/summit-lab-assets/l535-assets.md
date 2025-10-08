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
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 24%

---

# Summit Lab L535 - Aide-mémoire

Cette page contient du texte et des liens utilisés dans le L535 Summit Lab. Cela vous permet de copier et coller le contenu dans vos messages Journey Optimizer.

## Liens

* [Site Web de SecurFinancial](https://dsn.adobe.com/web/hausmann-FTTN?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsIm5hbWUiOiJBbm9ueW1vdXMiLCJpc1N1cGVyVXNlciI6ZmFsc2UsImlzc3VlciI6ImhhdXNtYW5uIiwicHJvamVjdHMiOnsiaGF1c21hbm4tRlRUTiI6InZpZXcifSwiaWF0IjoxNzQwNzU2NTYxLCJleHAiOjE3NDMzNDg1NjF9.ryOTsqDH9B33436RlIo4AHFxx8aGjNEMqv9FAxLZb9U){target="_blank"}
* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:ajo-summit-lab/journey-optimizer/journeys){target="_blank"}
* Classeur [L535](/help/summit-labs/summit-lab-assets/assets/summit_lab_manual_l535-final-v4.pdf){target="_blank"}
* [Télécharger l’application](https://demo-system-next.s3.amazonaws.com/dxdemo/summit/index.html){target="_blank"}

## Copier-coller pour les exercices

### Exercice 2.1 - Se connecter à Journey Optimizer

Connectez-vous à l’aide des informations suivantes :

Adresse e-mail :    L535+*votre numéro de poste*@adobeeventlab.com

Mot de passe :       Adobe4Summit !


### Exercice 2.3 : composer l’e-mail

#### Prompt

```
Generate a welcome email for new SecurFinancial customers who just opened a new checking account. 
Add a call to action to install the SecurFinancial mobile app.
```

### Exercice 3.1 : appliquer du contenu dynamique au message SMS

#### Code

```
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

### Exercice 4.2 - Configurer les traitements

#### Titre

```
Welcome to SecurFinancial
```

#### Corps de texte

```
Did you know you can find an ATM near in the SecurFinancial app? Try it now!
```

#### URL

```
dxdemo://atm
```

### Exercice 6 - Cartes de contenu

#### Titre

```
Welcome to SecurFinancial!
```

#### Corps

```
Thank you for downloading the app. You can find ATMs, track your spending and more. All within the app.
```

#### URL de médias

```
https://demo-system-next.s3.amazonaws.com/assets/securfinancial/home-loan.jpg
```

#### Titre du bouton

```
Find ATMs
```

#### URL cible

```
dxdemo://atm
```

## Images

![Logo SecureFinancial](/help/summit-labs/summit-lab-assets/assets/SecureFinancial-logo.png)


![Téléphone portable](/help/summit-labs/summit-lab-assets/assets/online-banking-app-01.png)
