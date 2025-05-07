---
title: Création de balises Adobe Experience Platform
description: Création d’audiences AJO en fonction des préférences d’investissement des utilisateurs (actions, obligations, CD)
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-05T00:00:00Z
jira: KT-17923
source-git-commit: 9695a4db0d0caa44a8c7d49e069320309ffc40a6
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Création d’un Adobe Experience Platform

Adobe Launch est configuré sur la page web pour charger le SDK web Adobe Experience Platform, ce qui permet à l’appel de l’API sendEvent de déclencher des expériences personnalisées. Cette configuration garantit que les bibliothèques côté client nécessaires sont correctement initialisées, ce qui permet une interaction en temps réel avec Adobe Journey Optimizer pour la diffusion d’offres.

* Connexion à la collecte de données
* Cliquez sur Balises -> Nouvelle propriété .
* Créez une balise Adobe Experience Platform appelée Service ECID.

* Ajoutez les extensions suivantes à la balise .
  ![tags-extensions](assets/ecid-tag.png)

* Veillez à configurer le SDK Web Adobe Experience Platform pour utiliser l’environnement approprié et le flux de données Financial Advisors créé dans le tutoriel précédent
  ![configuration-sdk-web](assets/web-sdk-configuration.png)

* Aucune configuration supplémentaire n’est nécessaire pour les extensions Core et de la couche de données client Adobe

## Créer un élément de données

L’élément de données ECID dans Adobe Launch est créé uniquement à des fins de débogage et de test. Il permet aux développeurs d’afficher l’Experience Cloud ID attribué à la session de navigateur d’un utilisateur, ce qui peut aider à valider la combinaison d’identités et à s’assurer que les appels sendEvent sont associés au profil correct. Cet élément n’est pas nécessaire au fonctionnement de la personnalisation, mais il est utile lors de l’implémentation et de l’assurance qualité

![ecid](assets/ecid-data-element.png)


## Inclure les balises AEP dans la page HTML

Création et publication des balises Adobe Experience Platform

Lorsqu’une propriété AEP Tags est publiée, Adobe vous fournit une balise de script que vous devez placer dans votre ``` <head>``` HTML ou au bas des balises ``` <body>```.

* Accédez à la propriété Balises (service ECID) .

* Cliquez sur Environnements et cliquez sur l’icône d’installation de l’environnement souhaité (par exemple, Développement, Évaluation, Production).

* Notez le code incorporé. Ce code doit être placé juste avant la balise ```</body>``` de fermeture dans la page HTML.

