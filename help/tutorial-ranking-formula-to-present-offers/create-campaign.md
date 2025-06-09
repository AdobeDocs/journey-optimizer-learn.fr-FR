---
title: Création d’une campagne
description: Découvrez comment une campagne AJO connecte les audiences, les politiques de décision et les canaux pour diffuser des offres personnalisées au bon moment sur les points de contact des clients.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
recommendations: noDisplay, noCatalog
jira: KT-18188
exl-id: deb16dd5-23cd-495a-ac91-d22fd77f49bd
source-git-commit: 7d812f589172c5052a1e9bfcf6a99d0769a6c2c7
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 1%

---

# Créer une campagne

Pour diffuser des offres personnalisées aux utilisateurs sur la page web, une campagne a été créée dans Adobe Journey Optimizer et configurée avec le canal correct : canal web. Cette configuration garantit que les offres sont diffusées aux utilisateurs interagissant avec le site web par le biais de la prise de décision en temps réel.

Dans cette campagne, une politique de décision a été définie pour contrôler la manière dont les offres sont sélectionnées. La politique de décision comprend une stratégie de sélection qui consiste à :

Une collection d’éléments d’offre (par exemple, en fonction du code postal ou du revenu),

des règles d’éligibilité qui déterminent les offres qui s’appliquent à un utilisateur, et

Une formule de classement qui attribue des scores aux offres éligibles pour prioriser les plus pertinentes.

Lorsqu’un utilisateur connecté visite le site, une demande de personnalisation est envoyée à AJO. En fonction de l’identité regroupée et des attributs de profil de l’utilisateur (tels que le code postal et le revenu annuel), la politique de décision évalue toutes les offres disponibles. Il applique la stratégie de sélection et la logique de classement pour déterminer la meilleure correspondance.

Le résultat est un ensemble d’offres personnalisées, renvoyées sous forme de contenu HTML et affichées pour l’utilisateur dans un carrousel du site web, offrant une expérience personnalisée en temps réel et transparente.


## Étapes de haut niveau pour créer une campagne dans AJO

1. **Créer une configuration de canal**\
   Définissez où et comment les offres s’affichent (par exemple, une page web avec une expérience basée sur du code).
   - Connexion à Parcours Optimizer
Accédez à Administration ->Canaux ->Créer une configuration de canal
   - **Nom** : `finwise-web-personalization`\
     Identifie cette configuration pour la diffusion d&#39;offres web personnalisées de FinWise.

   - **Platform** : `Web`\
     Ciblée spécifiquement pour les navigateurs web. Aucun canal mobile n’est activé.

   - **Type d’expérience** : `Code-based experience`\
     Les offres ne sont pas directement injectées dans le DOM. Au lieu de cela, AJO renvoie une HTML brute qui est analysée à l’aide d’un JavaScript personnalisé.

   - **URL de la page** : `http://localhost:3000/formula.html`\
     Le canal est configuré pour une page de test spécifique utilisée pendant le développement.

   - **Emplacement sur la page** : `offers-div`\
     Les offres renvoyées sont analysées et rendues dynamiquement dans ce conteneur à l’aide de la logique frontale.

   - **Format de contenu** : `HTML`\
     Les offres sont diffusées sous forme de fragments HTML bruts, ce qui permet de contrôler entièrement leur style, leur filtrage et leur affichage.


2. **Démarrer une nouvelle campagne**\
   Accédez à la section Campagnes et créez une campagne marketing planifiée. Nommez la campagne de manière appropriée.


3. **Ajouter une action**\
   Ajoutez une action d’expérience basée sur le code et liez l’action à une configuration de canal créée précédemment.



4. **Audience**\
   Tous les visiteurs (par défaut).

   Type d’identité : ECID (Experience Cloud ID)
Ce paramètre utilise l’ECID comme identité principale pour reconnaître les utilisateurs. Lorsque l’assemblage des identités est en place, l’ECID est lié à l’ID CRM pour Personalized Targeting Sélectionnez ou créez une politique de décision qui définit la logique d’offre.

5. **Politique de décision**


   L’action est liée à une **politique de décision** qui définit la manière dont les offres sont sélectionnées et le nombre d’offres renvoyées pour affichage. Cette stratégie utilise une **Stratégie de sélection** qui a été créée précédemment dans le tutoriel.

   Pour insérer la politique de décision, cliquez sur **_Modifier le contenu_** dans les sections Actions , puis cliquez sur **_Modifier le code_** pour ouvrir l’éditeur de personnalisation.

   Sélectionnez l’icône _&#x200B;**Politique de décision**&#x200B;_ à gauche et cliquez sur le bouton **Ajouter une politique de décision** pour ouvrir l’écran **Créer une politique de décision**. Attribuez un nom significatif à la politique de décision et sélectionnez le nombre d’éléments que la politique de décision doit renvoyer. La valeur par défaut est 1.
Cliquez sur **_suivant_**, ajoutez la stratégie de sélection créée à l’étape précédente à la politique de décision et cliquez sur **suivant** pour terminer le processus de création de la politique de décision. Veillez à sélectionner l’offre de secours appropriée.

6. **Insérer une politique de décision**

   ![personalization-editor](assets/personalization-editor.png)

   Insérez la nouvelle politique de décision en cliquant sur le bouton _&#x200B;**Insérer une politique**&#x200B;_. Vous insérez ainsi une boucle for dans l’éditeur de personnalisation sur le côté droit.
Placez votre curseur entre les boucles de la ligne 2 et insérez le texte de l&#39;offre en accédant à l&#39;offre en descendant la `tenant name`


   Le code Handlebars effectue une boucle sur les offres renvoyées par une politique de décision spécifique dans Adobe Journey Optimizer et crée une `<div>` pour chaque offre. Chaque `<div>` utilise un attribut data-tags avec le nom interne de l’offre pour aider le groupe de carrousel et organiser les offres par catégorie pour une navigation fluide. Le contenu de chaque `<div>` affiche le texte de l’offre personnalisée, ce qui permet une présentation dynamique et visuellement segmentée de plusieurs offres.


7. **Publier la campagne**\
   Activez la campagne pour commencer à diffuser des offres personnalisées en temps réel.

![img](assets/personalization-editor.png)
