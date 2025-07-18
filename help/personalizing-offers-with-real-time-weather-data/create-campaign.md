---
title: Création d’une campagne
description: Découvrez comment une campagne AJO connecte les audiences, les politiques de décision et les canaux pour diffuser des offres personnalisées au bon moment sur les points de contact des clients.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18258
exl-id: c3e4f760-9b10-4a99-bc53-9245e76c1bab
source-git-commit: 95a8abd08fbf57900870826112b01a8cd375fe96
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 1%

---

# Créer une campagne

Pour diffuser des offres personnalisées aux utilisateurs sur la page web, une campagne a été créée dans Adobe Journey Optimizer et configurée avec le canal d’expérience basé sur le code approprié. Cette configuration garantit que les offres sont diffusées aux utilisateurs interagissant avec le site web par le biais de la prise de décision en temps réel.

Dans cette campagne, une politique de décision a été définie pour contrôler la manière dont les offres sont sélectionnées. La politique de décision comprend une stratégie de sélection qui consiste à :

- Une collection d’éléments d’offre (par exemple, basée sur des balises liées à la météo),
- des règles d’éligibilité qui déterminent les offres qui s’appliquent à un utilisateur, et
- Une formule de classement qui attribue des scores aux offres éligibles pour prioriser les plus pertinentes.

Lorsqu’un utilisateur visite le site web, le système détecte son emplacement et récupère la température actuelle à l’aide d’une API météorologique. Ces données de température sont ensuite envoyées à Adobe Experience Platform via le SDK Web (alliage). En fonction de ces données contextuelles en temps réel, Adobe Journey Optimizer évalue les offres prédéfinies qui sont balisées pour des conditions météorologiques spécifiques, telles que le chaud, le doux ou le froid. L’offre la plus pertinente à l’aide de la stratégie de sélection et de la formule de classement est automatiquement rendue sur la page web à l’aide du moteur de prise de décision d’Adobe, ce qui garantit que l’utilisateur reçoit un contenu personnalisé adapté à la météo actuelle de sa zone.


## Étapes de haut niveau pour créer une campagne dans AJO

- Création d’une configuration de canal
   - Définissez où et comment les offres s’affichent (par exemple, une page web avec une expérience basée sur du code).
   - Connexion à Parcours Optimizer
   - Accédez à _**Administration ->Canaux->Créer une configuration de canal**_
   - **Nom** : `offers-by-weather`\
     Identifie cette configuration pour la diffusion d&#39;offres web personnalisées.
- **Canal** :
  `Code-based experience`\
  Les offres ne sont pas directement injectées dans le DOM. Au lieu de cela, AJO renvoie une HTML brute qui est analysée à l’aide d’un JavaScript personnalisé.
- **Platform** : `Web`\
  Ciblée spécifiquement pour les navigateurs web. Aucun canal mobile n’est activé.

- **URL de la page** : `https://gbedekar489.github.io/weather/weather-offers.html`\
  Le canal est configuré pour une page de test spécifique utilisée pendant le développement.
- **Emplacement sur la page** : `offerContainer`\
  Les offres renvoyées sont analysées et rendues dynamiquement dans ce conteneur à l’aide de la logique frontale.

- **Format de contenu** : `HTML`\
  Les offres sont diffusées sous forme de fragments HTML bruts, ce qui permet de contrôler entièrement leur style, leur filtrage et leur affichage.


- **Démarrer une nouvelle campagne**
   - Accédez à la section Campagnes et créez une campagne marketing planifiée. Nommez la campagne de manière appropriée.
   - **Ajouter une action**
      - Ajoutez une action d’expérience basée sur le code et liez l’action à une configuration de canal créée précédemment.



   - **Audience**
      - Tous les visiteurs (par défaut).
      - Type d’identité : ECID (Experience Cloud ID)
Ce paramètre utilise l’ECID comme identité principale pour reconnaître les utilisateurs.


- **Créer une politique de décision**
   - L’action est liée à une **politique de décision** qui définit la manière dont les offres sont sélectionnées et le nombre d’offres renvoyées pour affichage. Cette stratégie utilise une **Stratégie de sélection** qui a été créée précédemment dans le tutoriel.
   - Pour insérer la politique de décision, cliquez sur **_Modifier le contenu_** dans les sections Actions , puis cliquez sur **_Modifier le code_** pour ouvrir l’éditeur de personnalisation.
   - Sélectionnez l’icône _**Politique de décision**_ à gauche et cliquez sur le bouton **Ajouter une politique de décision** pour ouvrir l’écran **Créer une politique de décision**. Attribuez un nom significatif à la politique de décision et sélectionnez le nombre d’éléments que la politique de décision doit renvoyer. La valeur par défaut est 1.
   - Cliquez sur **_suivant_**, ajoutez la stratégie de sélection créée à l’étape précédente à la politique de décision et cliquez sur **suivant** pour terminer le processus de création de la politique de décision. Aucune offre de secours n’a été associée à la politique de décision.



- **Insérer une politique de décision**
  ![personalization-editor](assets/personalization-editor.png)

  Insérez la nouvelle politique de décision en cliquant sur le bouton _**Insérer une politique**_. Vous insérez ainsi une boucle for dans l’éditeur de personnalisation sur le côté droit.
Placez votre curseur entre les boucles de la ligne 2 et insérez le texte de l&#39;offre en accédant à l&#39;offre en descendant dans la `tenant name`. Encapsulez l’offre dans une balise &lt;div> avec l’élément d’offre de classe comme illustré dans la capture d’écran.



- **Publier la campagne**\
  Activez la campagne pour commencer à diffuser des offres personnalisées en temps réel.
