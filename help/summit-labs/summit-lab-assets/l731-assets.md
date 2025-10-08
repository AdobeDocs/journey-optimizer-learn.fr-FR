---
title: Aide-mémoire L731
description: Cette page comporte du texte et des liens utilisés dans le L731 Summit Lab.
feature: In App, SMS, Push, Email
doc-type: article
role: User
level: Beginner
recommendations: noDisplay, noCatalog
hide: true
hidefromtoc: true
exl-id: ffc5e8c8-8729-4e7e-aa51-d74f91b0cf29
source-git-commit: 201470e35095b38617d1a1bb5d7b16c1e60f431e
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 98%

---

# Summit Lab L731 - Aide-mémoire

Cette page comporte du texte et des liens utilisés dans le L731 Summit Lab. Cela vous permet de copier et coller le contenu dans vos messages Journey Optimizer.

## Exercice 1.1 : télécharger et installer l’application

Scanner le code QR pour télécharger l’application

>[!BEGINTABS]

>[!TAB iOS]

![Code QR pour iOS.](/help/assets/lab731-ios-qr-code.png)

>[!IMPORTANT]
>
>Si vous êtes invité(e) à présenter le code d’échange, fermez l’application TestFlight et scannez à nouveau le code QR.
>
>Autorisez les notifications.
>

Le processus vous invite à installer Testflight, en suivant les étapes 1 à 4. Une fois Testflight installé, suivez les étapes 5 à 8 pour installer l’application Vegas Stay :

<table>
<tr>
</tr>
<tr>
<td>
 <div>
      <p>
      <b>Étape 1 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-1.png"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Étape 2 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-2.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Étape 3 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-3.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <b>Étape 4 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-4.PNG"/>
      </a>
      </div>
  </td>
  </tr>
  <tr>
<td>
 <div>
      <p>
      <b>Étape 5 </b>
      <p>
      <a>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-5.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Étape 6 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-6.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Étape 7 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-7.PNG"/>
      </a>
      </div>
  </td>
  <td>
 <div>
      <p>
      <a>
      <b>Étape 8 </b>
      <p>
        <img alt="testflight 1" src="../assets/l731-ios-install/ios-install-8.PNG"/>
      </a>
      </div>
  </td>
  </tr>
</table>

>[!TAB Android]

![Code QR pour Android.](/help/assets/lab731-android-qr-code.png)

L’application n’étant pas enregistrée auprès de la boutique Google Play, vous recevez un message d’avertissement :

![Écran d’avertissement Android.](/help/assets/lab731-install-android.png)

Cliquez sur **Installer quand même**.

>[!ENDTABS]

## Exercice 1 : se connecter à Adobe Journey Optimizer

[Cliquez ici pour vous connecter à Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-2023-ajo-lab/journey-optimizer/home){target="_blank"}.

**Identifiants de connexion**

* **Nom d’utilisateur :** `L731+<your seat number>@summitlab.us` (exemple : L731+001@summitlab.us)
* **Mot de passe :** Adobe2023!


## Exercice 2 : créer une campagne in-app

| Section | Champ | Texte | Liens |
|----|----|----|----|
| **Propriétés** | Nom de la campagne | `<your seat number> Vegas Stay Campaign` |  |
| **Triggers** | État | booknow |  |
| **Modifier le contenu :** médias | Option URL de médias |  | https://i.ibb.co/NstLhjW/Firefly-Poster-with-heading-Adobe-Max-84773.jpg |
| **Modifier le contenu :** contenu | Titre | Bénéficiez du tarif préférentiel ! |  |
| **Modifier le contenu :** contenu | Corps | Adobe Max revient à Las Vegas. Préparez-vous à des interventions passionnantes, à des sessions pour accroître vos compétences et à de nouvelles rencontres. Réservez dès maintenant votre suite et profitez d’une remise de 10 %. |  |
| **Modifier le contenu :** boutons | Bouton | Bénéficiez d’une remise de 10 % ! | lab://booking?suite=presidential&amp;discount=10 |
| **Modifier le contenu: ** boutons | Événement d’interaction | Appel à l’action in-app |  |
| **Prévisualisation sur l’appareil** | URL de base à utiliser pour la prévisualisation sur l’appareil |  | **iOS :** lab:// <br>**Android** : https://lab |

## Exercice 3 : créer une notification push

| Champ | Texte | Liens |
|----|----|----|
| Nom de la campagne | **`<your seat number> Max Push Campaign`** |  |
| Titre | Hé ! |  |
| Corps | Saviez-vous qu’Adobe Max revient à Vegas. Réservez votre chambre maintenant et bénéficiez d’une remise de 10 %. |  |
| Option URL de médias |  | https://i.ibb.co/1M0BnZn/Firefly-Big-conference-big-stage-with-ADBE-text-on-screen-40178.jpg |
