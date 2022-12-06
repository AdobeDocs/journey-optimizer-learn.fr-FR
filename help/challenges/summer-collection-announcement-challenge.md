---
title: Créer une annonce de collection d’été - Défi
description: Envoyez une annonce de collection d’été à un segment de clients existants afin de promouvoir la nouvelle collection d’été Luma.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
exl-id: ae457be7-2c67-4950-a072-1d7030b0e17b
source-git-commit: fa78749a6b768bd637ef5b5a7cda907a7b2030f4
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 3%

---

# Créer une annonce de collection d’été - Défi

![Bannière d’annonce de collection d’été AJO](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Défi | Créer une annonce de collection d’été |
|---|---|
| Personne | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importation et création de contenu d’e-mail HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Cas d’utilisation : lecture de segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Ressources à télécharger | [Fichiers d’email de collection saisonnière](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

## L&#39;histoire

Luma, une société de vêtements de fiction pour les sportifs, cherche à promouvoir ses dernières collections de vêtements et d’équipements et à stimuler les ventes pour les clients existants. Luma lance la nouvelle collection d’été et souhaite spécifiquement cibler différents segments de clients.

## Votre défi

L’équipe marketing de Luma vous demande de mettre en oeuvre une campagne marketing de collecte d’été dans Journey Optimizer. Votre défi est de :

* Créez un segment définissant les profils qui peuvent recevoir la promotion.
* Créer le parcours

### Étape 1 : Définition du segment - Principaux clients

>[!BEGINTABS]

>[!TAB Tâche]

#### Création d’un segment dans Journey Optimizer

* Créez un segment dans Journey Optimizer appelé `Active Customers`.
* Le segment ne doit inclure que les principaux clients Luma.
* Les clients principaux sont définis comme des clients ayant un niveau dans le programme de fidélité de Luma (argent, or, platine ou diamant).


>[!TAB Critères de réussite]

Dans le créateur de segments, vous pouvez consulter l’estimation du nombre de profils qualifiés. Si vous travaillez avec les données d’environnement de test d’entraînement, vous disposez d’environ 753 profils qualifiés sur 1,29 K.

>[!NOTE]
>L’affichage de l’appartenance au segment pour les profils existants peut prendre jusqu’à 24 heures, car les profils existants doivent être renvoyés.

**Un profil qualifié a été ajouté au segment :**

Vous pouvez vérifier les profils qui ont été ajoutés au segment en accédant à l’un des profils répertoriés dans la vue Détails de votre segment.

Sur la page du profil, cochez la case [!UICONTROL Attributs] pour confirmer qu’ils remplissent les critères suivants : Le niveau doit être en argent, or, platine ou diamant.

![Attributs de profil](assets/C1-S1-profile-attributes.png)

Vous pouvez également vérifier les [!UICONTROL abonnement au segment] tab : Votre segment doit être répertorié.

![Appartenance à un segment](assets/C1-S1-profile-segment-membership.png)

>[!TAB Vérifier votre travail]

Champs de segment : [!UICONTROL Attributs] > [!UICONTROL Profil XDM individuel] > [!UICONTROL Fidélité] > [!UICONTROL Niveau]

Voici à quoi votre segment doit ressembler :

![Segment - Principaux clients](/help/challenges/assets/C1-S1.png)

Le code doit se présenter comme suit :

```javascript
stringCompare("equals", loyalty.tier, ["diamond", "gold", "platinum", "silver"], false)
```

>[!ENDTABS]


### Étape 2 : Créer un Parcours - Annonce de collection d’été

>[!BEGINTABS]

>[!TAB Tâche]

#### Envoyer une annonce de collection d’été

Une agence vous a fourni quatre fichiers HTML avec la conception des emails :

* SeasonalCollectionEmail.html
* Courrier électronique de collection pour hommes Luma
* Courrier électronique de la collection des femmes Luma
* Luma - 20 % des e-mails de collecte

1. [Téléchargement des fichiers d’email de la collection saisonnière](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip).

2. Créez un parcours appelé `Luma - Summer collection announcement` selon les directives suivantes :

   1. Envoyer *Luma - Nouvelle annonce de la collection d’été* e-mail à la fonction *Clients principaux* , représentant 10 % de l’audience en tant que groupe témoin
      * Titre du message `Luma - Summer Collection Announcement`.
      * Objet `(recipient's first name), the new Luma summer collection is here!`.
      * Utilisation du fichier de HTML fourni *SeasonalCollectionEmail.html* pour le corps de l’email.
   2. Patientez deux jours, puis envoyez un email de relance avec du contenu plus ciblé :
      * Les clients masculins doivent recevoir la variable **Collection Hommes Luma** e-mail.
         * Titre du message : `Luma Men's Collection`
         * Objet: `(recipient's first name), explore Men's New athletic gear!`
         * Corps de l&#39;email : *MensCollectionEmail.html* pour le corps de l’email.
      * Les clientes doivent recevoir la variable **Collection Femmes Luma** e-mail.
         * Titre du message : `Luma Women's Collection`
         * Objet: `(recipient's first name), explore Luma's Women Collection!`
         * Corps de l&#39;email : *WomensCollectionEmail.html*
      * Les autres clients doivent recevoir la variable **Luma - 20 % de la collection** e-mail.
         * Titre du message : `Luma - 20 % off Collection`
         * Objet: `(recipient's first name), enjoy 20% off sales!`
         * Corps de l&#39;email : *20OffCollectionEmail.html*
   3. Après avoir envoyé les emails ciblés ci-dessus, patientez deux jours pour ouvrir l&#39;email.
   4. Si l&#39;email ciblé n&#39;est pas ouvert dans les 2 jours, envoyez la variable **Luma - 20 % de l’e-mail Collection** comme tentative de reciblage finale


>[!TAB Critères de réussite]

#### Aperçu des emails

**Message électronique #1 - Luma - Annonce de collection d’été**

Prévisualiser l&#39;email :

1. Ajoutez un profil de test : Louise Petti :
   1. Espace de noms d’identité : *Identifiant Luma CRM*
   2. Valeur d’identité : *d1f132f9f9502bba047a6ec86c4b61f9*

Résultat:
* L’objet doit être le suivant : Louise, la nouvelle collection Luma est là !
* Le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Nouvelle annonce de collection saisonnière](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**Message électronique #2 - Collection Hommes Luma**

Envoyez-vous un bon à tirer :

1. Ajoutez un profil de test : Stanleigh Stooke :
   1. Espace de noms d’identité : *Identifiant Luma CRM*
   1. Valeur de l’identité: `4f34057d9d9e792c28ba18ecae378e98`
1. Sélectionnez le profil de test : Stanleigh Stooke
1. Envoyer un bon à tirer à vous-même

Résultat:\
Vous devriez recevoir un email. Le sujet devrait être : &quot;Stanleigh, explore la nouvelle tenue athlétique masculine !&quot; et le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Collection Hommes Luma](/help/challenges/assets/email-assets/MensCollectionEmail.html)

>[!NOTE]
>Cela peut prendre quelques minutes pour que vous receviez le bon à tirer.

**Message électronique #3 - Collection Femmes Luma**

Prévisualisez l&#39;email avec le profil de test &quot;Louise Petti&quot;.

* L’objet doit être le suivant : *Louise, découvrez la collection Femmes de Luma !*
* Le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Collection Femmes Luma](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**Message électronique #4 - Luma 20 % hors collection**

Prévisualisez l&#39;email avec le profil de test &quot;Louise Petti&quot;.

* L’objet doit être le suivant : *Louise, profitez de 20% de remises !*
* Le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Luma 20 % hors collection](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)


#### Tester votre parcours

>[!IMPORTANT]
>
>Avant de mettre le parcours en mode test :
>
>1. Assurez-vous que l’espace de noms de l’activité Lecture de segment est défini sur **Luma CRM id(lumaCrmId)**
>1. Pour chaque email, remplacez les paramètres par défaut Email des emails afin qu’ils soient envoyés à votre adresse email :
   >    * Affichez les valeurs masquées en cliquant sur le symbole de l’oeil.
   >    * Dans les paramètres de l’e-mail, cliquez sur le symbole T (activer le remplacement des paramètres).

      >
      >      ![Remplacer les paramètres de courrier électronique](/help/challenges/assets/c3-override-email-paramters.jpg)
   > 
   >    * Cliquez dans le champ Adresse
   >    * Dans l’écran suivant, ajoutez votre adresse électronique entre parenthèses : `"yourname@yourdomain"` dans l’éditeur d’expression, puis cliquez sur ok.

>


Testez le parcours et envoyez les emails à votre compte :

1. Mise du parcours en mode test
2. Sélection d’un seul profil à la fois
3. Temps d’attente : Définissez le minuteur sur 120 secondes (saisissez-le dans le champ ).
4. Entrée du profil de déclenchement
5. Vous pouvez tester chaque branche à l’aide de l’une des méthodes suivantes : *Identifiants Luma CRM* comme identifiants de profil :
   * Femme : Leora Dietsche, Identity Value :`a8f14eab3b483c2b96171b575ecd90b1`
   * Homme : Stanleigh Stooke, Identity Value : `4f34057d9d9e792c28ba18ecae378e98`
   * Genre non spécifié : Louise Petti, Identity Value : `d1f132f9f9502bba047a6ec86c4b61f9`

6. Une fois que vous avez déclenché l’entrée du profil, vous devriez recevoir le premier email. L’en-tête doit être personnalisé en fonction du profil que vous avez choisi.
7. Le parcours doit continuer dans la branche correspondante et vous devriez recevoir l’e-mail correspondant (par exemple, si vous avez choisi Jenna, vous devriez recevoir l’e-mail &quot;Luma Women’s Collection&quot;).
8. Ouvrez le deuxième email et le parcours doit se terminer.
9. Vous pouvez répéter l’étape 4. - 7. pour les trois profils afin de vérifier si toutes vos branches fonctionnent correctement.
10. Pour tester les expirations de délai, définissez le délai d’attente sur 30 secondes et déclenchez à nouveau l’entrée.
11. N’ouvrez pas les emails que vous recevez (ne prévisualisez pas l’email (!)) et laisser le temps d’attente s’écouler.

Vous devriez recevoir les emails suivants :

* Luma - Nouvelle annonce de collection saisonnière
* Selon le profil de test utilisé, vous devriez recevoir l’un des courriers électroniques suivants :
   * Leora : Collection Femmes Luma
   * Stanleigh : Collection Hommes Luma
   * Louise : Luma - 20 % de réduction de la collecte
* Si vous n’avez pas ouvert le deuxième email : La Luma - 20 % de réduction de la collecte

>[!TAB Vérifier votre travail]

Voici à quoi votre parcours doit ressembler :

![Parcours](/help/challenges/assets/c3-j1-journey.png)

**Condition - Groupe de contrôle :**

![Population témoin](/help/challenges/assets/c3-j1-condition-control-group.png)

**Condition - Genre :**\

![Condition - Genre](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]
