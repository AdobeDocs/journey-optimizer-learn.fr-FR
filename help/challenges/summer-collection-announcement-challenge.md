---
title: Créer une annonce de collection d’été - Défi
description: Envoyez une annonce de collection d’été à un segment de clients existants afin de promouvoir la nouvelle collection d’été Luma.
kt: 8109
role: User
level: Beginner
last-substantial-update: 2022-11-16T00:00:00Z
hide: true
source-git-commit: 3cd8b1a5b98adbe822cd82db8c27137b534c16e3
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 2%

---


# Créer une annonce de collection d’été - Défi

![Bannière d’annonce de collection d’été AJO](/help/challenges/assets/email-assets/luma-transactional-onboarding-3.png)

| Défi | Créer une annonce de collection d’été |
|---|---|
| Personne | Gestionnaire de parcours |
| Compétences requises | <ul><li>[Créer des segments](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/profiles-segments-subscriptions/create-segments.html?lang=en)</li><li> [Importation et création de contenu d’e-mail HTML](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-messages/create-emails/import-and-author-html-email-content.html?lang=en)</li><li>[Cas d’utilisation : lecture de segment](https://experienceleague.adobe.com/docs/journey-optimizer-learn/tutorials/create-journeys/use-case-read-segment.html?lang=en)</li> |
| Ressources à télécharger | [Fichiers d’email de collection saisonnière](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip) |

>[!NOTE]
> Les exercices ont été développés à partir des données d’exemple de Luma. Nous vous recommandons de configurer un environnement de test d’entraînement, configuré avec les exemples de données. Consultez le tutoriel [Importation de données d’exemple dans Adobe Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/import-sample-data.html?lang=fr) pour obtenir des instructions détaillées.

## L&#39;histoire

Luma, une société de vêtements de fiction pour les sportifs, cherche à promouvoir ses dernières collections de vêtements et d’équipements et à stimuler les ventes pour les clients existants. Luma lance la nouvelle collection d’été et souhaite spécifiquement cibler différents segments de clients.

## Votre défi

L’équipe marketing de Luma vous demande de mettre en oeuvre une campagne marketing de collecte d’été dans Journey Optimizer.

Le défi consiste à créer un parcours dans Journey Optimizer. Plus précisément, vous devez créer le segment requis, créer quatre messages et créer le parcours.

>[!NOTE]
> Si vous travaillez dans un environnement de test de formation partagé, il est recommandé d’ajouter votre nom ou vos initiales en tant que préfixe au nom de tout élément que vous créez.

### Étape 1 : Définition du segment - Principaux clients

>[!BEGINTABS]

>[!TAB Tâche]

Créez un segment dans Journey Optimizer appelé **votre nom - Principaux clients**.

* Le segment ne doit inclure que les principaux clients Luma.
* Les clients principaux sont définis comme des clients ayant un niveau dans le programme de fidélité de Luma (argent, or, platine ou diamant).


>[!TAB Critères de réussite]

Dans le créateur de segments, vous pouvez consulter l’estimation du nombre de profils qualifiés. Si vous travaillez dans un environnement de test d’entraînement qui utilise les données d’exemple Luma, la variable [!UICONTROL estimation des profils qualifiés] devrait être environ 292 profils sur 500.

**Un profil qualifié a été ajouté au segment :**

Vous pouvez vérifier les profils qui ont été ajoutés au segment en accédant à l’un des profils répertoriés dans la vue Détails de votre segment.

Sur la page du profil, cochez la case [!UICONTROL Attributs] pour confirmer qu’ils remplissent les critères suivants : Le niveau doit être en argent, or, platine ou diamant.

![Attributs de profil](assets/C1-S1-profile-attributes.png)

Vous pouvez également vérifier les [!UICONTROL abonnement au segment] tab : Votre segment doit être répertorié.

>[!NOTE]
>L’affichage de l’appartenance au segment pour les profils existants peut prendre jusqu’à 24 heures, car les profils existants doivent être renvoyés.

![Appartenance à un segment](assets/C1-S1-profile-segment-membership.png)

>[!TAB Vérifier votre travail]

Champs de segment : [!UICONTROL Attributs] > [!UICONTROL Profil XDM individuel] > [!UICONTROL Fidélité] > [!UICONTROL Niveau]

Voici à quoi votre segment doit ressembler :

![Segment - Principaux clients](/help/challenges/assets/C1-S1.png)

Vérifiez le code dans le coin inférieur droit de l’écran Modifier le segment, sous Événements.

Le code doit se présenter comme suit :

```javascript
loyalty.tier.equals("diamond", false) or loyalty.tier.equals("gold", false) or loyalty.tier.equals("platinum", false) or loyalty.tier.equals("silver", false)
```

>[!ENDTABS]


### Étape 2 : Créer un Parcours - Annonce de collection d’été

>[!BEGINTABS]

>[!TAB Tâche]

Envoyez une annonce de collection d’été à un segment d’email des clients existants faisant la promotion de la nouvelle collection d’été Luma.&quot;

Une agence vous a fourni quatre fichiers HTML avec la conception des emails : [Téléchargement des fichiers d’email de la collection saisonnière](/help/challenges/assets/email-assets/emails-seasonal-collection-announcement.zip)

Créez un parcours appelé `(your name) - Summer collection announcement` selon les directives suivantes :

1. Envoyer Luma : nouvel e-mail d’annonce de collecte saisonnière au segment Clients Principal de Luma, qui représente 10 % de l’audience en tant que groupe témoin
   * Titre du message `(your name)_Luma New Seasonal Collection Announcement`.
   * Objet `(recipient's first name), the new Luma collection is here!`.
   * Utilisation du fichier de HTML fourni *SeasonalCollectionEmail.html* pour le corps de l’email.
2. Patientez deux jours, puis envoyez un email de relance avec du contenu plus ciblé :
   * Les clients masculins doivent recevoir la variable **Courrier électronique de collection pour hommes Luma**
      * Titre du message : **(votre nom)_Collection Hommes Luma**
      * Objet : **(prénom du destinataire), découvrez la nouvelle tenue athlétique masculine !**
      * Corps de l&#39;email : *MensCollectionEmail.html* pour le corps de l’email.
   * Les clientes doivent recevoir la variable **Courrier électronique de la collection des femmes Luma**
      * Titre du message : **(votre nom)_Collection de femmes Luma**
      * Objet : **(prénom du destinataire), explorez la collection Femmes de Luma !**
      * Corps de l&#39;email : *WomensCollectionEmail.html*
   * Les autres clients doivent recevoir la variable **Luma - 20 % des e-mails de collecte**
      * Titre du message : **(votre nom)_Luma - 20 % hors collection**
      * Objet :**(prénom du destinataire), profitez de 20% de réduction sur les ventes !**
      * Corps de l&#39;email : *20OffCollectionEmail.html*
3. Après avoir envoyé les emails ciblés ci-dessus, patientez deux jours pour ouvrir l&#39;email.
4. Si l&#39;email ciblé n&#39;est pas ouvert dans les 2 jours, envoyez la variable **Luma - 20 % de l’e-mail Collection** comme tentative de reciblage finale


>[!TAB Critères de réussite]

#### Aperçu des emails

**Message électronique #1- Nouvelle annonce de collection saisonnière**

Prévisualisez l&#39;email à l&#39;aide de l&#39;espace de noms Identity : *Email* et la valeur Identity : *Jenna_Palmer9530@emailsim.io*

* L’objet doit être le suivant : Jenna, la nouvelle collection Luma est là !
* Le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Nouvelle annonce de collection saisonnière](/help/challenges/assets/email-assets/SeasonalCollectionEmail.html)


**Message électronique #2 - Collection Hommes Luma**

Envoyer un bon à tirer à vous-même

* Entrez votre adresse électronique
* Sélectionnez le profil de test : Chris_Scott1244@emailsim.io

Vous devriez recevoir un email. Le sujet devrait être : &quot;Chris, découvrez le nouvel équipement sportif masculin !&quot; et le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Collection Hommes Luma](/help/challenges/assets/email-assets/MensCollectionEmail.html)

**Message électronique #3 - Collection Femmes Luma**

Prévisualisez l&#39;email à l&#39;aide de l&#39;espace de noms Identity : *Email* et la valeur Identity : *Jenna_Palmer9530@emailsim.io*

* L’objet doit être le suivant : *Jenna, découvrez la collection Femmes de Luma !*
* Le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Collection Femmes Luma](/help/challenges/assets/email-assets/WomensCollectionEmail.html)


**Message électronique #4 - Luma 20 % hors collection**

Prévisualisez l&#39;email à l&#39;aide de l&#39;espace de noms Identity : *Email* et la valeur Identity : *Benny_Steer4909@emailsim.io*

* L’objet doit être le suivant : *Benny, profitez de 20% de réduction sur les ventes !*
* Le corps de l’email doit correspondre à ce que vous avez vu dans l’aperçu : [Luma 20 % hors collection](/help/challenges/assets/email-assets/20OOffCollectionEmail.html)

**N&#39;oubliez pas de publier vos emails !**

#### Tester votre parcours

>[!IMPORTANT]
>
>Avant de mettre le parcours en mode test :
>
>1. Assurez-vous que l’espace de noms de l’activité Lecture de segment est défini sur Courrier électronique.
>1. Pour chaque email, remplacez les paramètres par défaut Email des emails afin qu’ils soient envoyés à votre adresse email :
>1. Affichez les valeurs masquées en cliquant sur le symbole de l’oeil.
>1. Dans les paramètres de l’e-mail, cliquez sur le symbole T (activer le remplacement des paramètres).

   >
   >      ![Remplacer les paramètres de courrier électronique](/help/challenges/assets/c3-override-email-paramters.jpg)
> 
>1. Cliquez dans le champ Adresse
>1. Dans l’écran suivant, ajoutez votre adresse électronique entre parenthèses : *yourname@yourdomain* dans l’éditeur d’expression, puis cliquez sur ok.

>


Testez le parcours et envoyez les emails à votre compte :

1. Mise du parcours en mode test
2. Sélection d’un seul profil à la fois
3. Temps d’attente : Définissez le minuteur sur 120 secondes (saisissez-le dans le champ ).
4. Entrée du profil de déclenchement
5. Vous pouvez tester chaque branche à l’aide de l’une des adresses électroniques suivantes comme identifiants de profil :
   * Femme : Jenna Palmer : Jenna_Palmer9530@emailsim.io
   * Homme : Chris Scott : Chris_Scott1244@emailsim.io
   * Genre non spécifié : Benny Steer : Benny_Steer4909@emailsim.io

6. Une fois que vous avez déclenché l’entrée du profil, vous devriez recevoir le premier email. L’en-tête doit être personnalisé en fonction du profil que vous avez choisi.
7. Le parcours doit continuer dans la branche correspondante et vous devriez recevoir l’e-mail correspondant (par exemple, si vous avez choisi Jenna, vous devriez recevoir l’e-mail &quot;Luma Women’s Collection&quot;).
8. Ouvrez le deuxième email et le parcours doit se terminer.
9. Vous pouvez répéter l’étape 4. - 7. pour les trois profils afin de vérifier si toutes vos branches fonctionnent correctement.
10. Pour tester les expirations de délai, définissez le délai d’attente sur 30 secondes et déclenchez à nouveau l’entrée.
11. N’ouvrez pas les emails que vous recevez (ne prévisualisez pas l’email (!)) et laisser le temps d’attente s’écouler.

Vous devriez recevoir les emails suivants :

* Luma - Nouvelle annonce de collection saisonnière
* Selon le profil de test utilisé, vous devriez recevoir l’un des courriers électroniques suivants :
   * Jenna : Collection Femmes Luma
   * Chris : Collection Hommes Luma
   * Benny : Luma - 20 % de réduction de la collecte
* Si vous n’avez pas ouvert le deuxième email : La Luma - 20 % de réduction de la collecte

>[!TAB Vérifier votre travail]

Voici à quoi votre parcours doit ressembler :

![Parcours](/help/challenges/assets/c3-j1-journey.png)

**Condition - Groupe de contrôle :**

![Population témoin](/help/challenges/assets/c3-j1-condition-control-group.png)

**Condition - Genre :**\

![Condition - Genre](/help/challenges/assets/c3-j1-condition-gender.png)
>[!ENDTABS]