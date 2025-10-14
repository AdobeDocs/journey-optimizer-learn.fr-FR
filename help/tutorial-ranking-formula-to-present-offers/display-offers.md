---
title: Créer une page web pour tester la solution
description: Page web pour tester les offres personnalisées diffusées à l’aide de la prise de décision.
role: User
level: Beginner
doc-type: Tutorial
feature: Decisioning
last-substantial-update: 2025-05-31T00:00:00Z
jira: KT-18188
recommendations: noDisplay, noCatalog
exl-id: 6b1eec78-153c-4ea5-acfe-2dcc6f1e6078
source-git-commit: 82d82b3aac2bf91e259b01fd8c6b4d6065f9640a
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 0%

---

# Créer une page web pour tester la solution

Cet exemple d’application simule un flux de connexion réel où les informations d’identification de l’utilisateur sont validées côté serveur avant l’envoi de l’identifiant de gestion de la relation client à Adobe Experience Platform (AEP). Un serveur Node.js local est utilisé pour diffuser en toute sécurité les pages web, gérer la logique d’authentification de base et éviter les restrictions du navigateur (telles que le blocage de l’accès aux fichiers locaux ou l’absence d’en-têtes CORS) qui pourraient interférer avec les fonctionnalités d’Adobe Launch ou de Web SDK. Cette configuration permet de s’assurer que l’expérience est plus proche d’un environnement de production réel.

Les offres personnalisées s’affichent uniquement après la connexion de l’utilisateur, moment où la combinaison d’identités entre l’identifiant CRM de l’utilisateur et l’ECID (Experience Cloud ID) est terminée. Ce regroupement des identités garantit que Adobe Journey Optimizer (AJO) peut reconnaître précisément le profil et renvoyer les offres ciblées.

Une fois la connexion établie, une demande de personnalisation est envoyée à AJO pour récupérer les offres disponibles pour l’utilisateur. Ces offres sont renvoyées sous la forme de fragments HTML, chacun étant incorporé avec un attribut data-tags=« ajo offer-vacance-based-cd zip-92128 return-high » - qui inclut le nom de l’offre et les détails de segmentation tels que le code postal et le niveau de revenu.

JavaScript analyse ensuite ces blocs HTML et les enveloppe chacun dans un conteneur d’élément de carrousel. Les éléments sont disposés horizontalement dans une piste de carrousel, ce qui permet une navigation glissante. Les boutons Précédent et Suivant (◀ et ▶) permettent aux utilisateurs et aux utilisatrices de parcourir les offres personnalisées une par une.

Cette configuration offre une expérience réactive et personnalisée, en veillant à ce que chaque utilisateur voit les offres pertinentes pour son profil financier, uniquement après que son identité a été groupée en toute sécurité sur toutes les plateformes.

## Tester cette solution

* Créez un dossier nommé ranking-form dans votre projet Node.js existant.

* Décompressez les fichiers [&#x200B; fournis dans ce dossier de formule de classement.](assets/ranking-formula.zip)

* Exécutez l’application en accédant au dossier et en démarrant le serveur :
   * `cd ranking-formula`

   * `node server.js`


* Ouvrez votre navigateur et accédez à http://localhost:3000/formula.html.

* Se connecter à l’aide d’alice/pass123

Comme Alice réside dans le code postal 92128, des offres adaptées à cet emplacement s’affichent.
