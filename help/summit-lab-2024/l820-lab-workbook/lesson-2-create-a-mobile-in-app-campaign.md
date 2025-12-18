---
title: 'Leçon 2 : créer une campagne in-app mobile'
description: Créez et déclenchez une campagne mobile in-app.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
exl-id: fe18eca7-229c-4867-ab34-1862bad63124
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 1%

---

# Leçon 2 : créer une campagne in-app mobile

Dans cette leçon, vous allez créer et déclencher des messages in-app mobiles.

## Objectifs d’apprentissage

* Comprendre comment les messages in-app sont déclenchés.
* Savoir comment créer une campagne mobile in-app.
* Déclenchez un message in-app.

## Exercice 2.1 : se connecter à Journey Optimizer

1. Ouvrir [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. Connectez-vous à l’aide des informations suivantes :
   <br>
   **Nom D’Utilisateur :** L820+**`<your seat number>`**@adobeeventlab.com
   **Password:**   Adobe2024 !
   <br>
Vous trouverez les détails de votre connexion sur le bureau de votre ordinateur de laboratoire. Utilisez l’Adobe ID et le mot de passe.
   ![ordinateur de bureau](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/desk-top.png)

   ![Écran de connexion](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. Vous pouvez ignorer les deux écrans suivants :
   <br>
   ![Numéro de téléphone](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   Fenêtre contextuelle de ![Personalization](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Vous devriez être connecté à Journey Optimizer et sur la page d’accueil :
>
>![Page d’accueil AJO](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## Exercice 2.2 : créer une campagne in-app mobile

Dans cet exercice, vous allez créer une campagne de messagerie in-app, qui sera déclenchée lors de l’ouverture de l’application.

1. Dans Journey Optimizer, dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Campagnes]**.

1. Cliquez sur **[!UICONTROL Créer une campagne]**.

   ![Créer une campagne](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Sur la page **[!UICONTROL Créer une campagne]**, dans la section **[!UICONTROL Action]**, cochez la case **[!UICONTROL Message in-app]**.

1. Dans la liste déroulante **[!UICONTROL Envoyer à]**, sélectionnez **[!DNL Mobile]**.

1. Dans le menu déroulant **[!UICONTROL Surface d’application]**, sélectionnez **[!DNL Frecopa Mobile App]**.

1. Cliquez sur **[!UICONTROL Créer]**.

   ![Surface d’application](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>Vous devriez maintenant être sur les propriétés de la campagne :
>
> ![Propriétés de la campagne](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## Exercice 2.3 : configurer votre campagne

### 2.3.1 [!UICONTROL section Propriétés]

Donnez un nom à votre campagne. Veillez à commencer le nom par votre numéro de place, afin de pouvoir retrouver facilement votre campagne.

Par exemple, si votre numéro de poste est 99 : `99 - Welcome Campaign`.

![section propriétés](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 Configurer votre règle de déclenchement personnalisée

1. Faites défiler l’écran jusqu’à la **[!UICONTROL section Triggers]**, puis cliquez sur **[!UICONTROL Modifier les triggers]**.

   ![modifier](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Dans le créateur de règles, cliquez sur **[!UICONTROL Lancement de l’application]** et dans la liste déroulante, sélectionnez *Envoi de données à Platform*.
   ![Envoyé à Data Platform](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Ajoutez une condition en cliquant sur **[!UICONTROL Ajouter une condition]**.

   ![bouton ajouter une condition](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Dans la liste déroulante **[!UICONTROL Sélectionner une caractéristique]**, sélectionnez **[!UICONTROL Type d’événement XDM]**.

   ![Type d’événement XDM](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. Dans le champ de texte suivant, ajoutez un *`<custom string value>`* dont vous pouvez vous souvenir.

1. Pour enregistrer la valeur, cliquez sur **[!UICONTROL Ajouter**] `<custom string value>`.

   Cette valeur de chaîne personnalisée est utilisée ultérieurement pour déclencher votre message.

   >[!TIP]
   > L’ajout de votre numéro de poste à la valeur de chaîne personnalisée la rend unique et plus facile à mémoriser.
   > 
   > Par exemple : `99exerciseTrigger`

   ![ajouter une valeur de chaîne de déclenchement personnalisée](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. Cliquez sur **[!UICONTROL Terminé]** en haut à droite.

>[!SUCCESS]
>
>Vous avez maintenant défini votre message in-app avec un événement déclencheur personnalisé.
>
>![Campagne avec déclencheur personnalisé défini](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 Modifier le contenu du message in-app

Dans la section **[!UICONTROL Action]**, cliquez sur **[!UICONTROL Modifier le contenu]**.

![bouton Modifier le contenu](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

L’éditeur [!UICONTROL Message in-app] s’affiche et vous permet de configurer le contenu du message in-app.

#### Disposition 2.3.3.1

Sélectionnez la disposition à appliquer à votre message.

Par exemple, cliquez sur **[!UICONTROL Modal]** pour faire de votre message in-app une disposition modale.

![&#x200B; bouton modal &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 Création de votre message et publication de votre campagne

1. Dans la section média , collez l&#39;URL suivante : `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
Lorsque vous cliquez en dehors du champ de valeur, votre image doit apparaître.

   ![média affiché dans l’aperçu](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-media.png)

2. Dans la section **[!UICONTROL Contenu]** suivante, ajoutez votre propre texte personnalisé que vous souhaitez afficher dans votre message pour les éléments **[!UICONTROL En-tête]** et **[!UICONTROL Corps]**.

   ![&#x200B; En-tête et corps &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-content.png)

3. Options supplémentaires :
   1. **Boutons:**

      ![Section Boutons](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. Dans cette section de l’éditeur, vous pouvez personnaliser le texte de votre bouton CTA en modifiant le champ Texte du bouton .

      2. Le champ **[!UICONTROL Événement d’interaction]** permet de définir la valeur transmise au SDK lorsque l’utilisateur appuie sur le CTA.

      3. Le champ **[!UICONTROL Cible]** permet de définir l’emplacement où vous souhaitez que le CTA emmène l’utilisateur. Cela inclut les URL et les liens profonds. Par exemple, vous pouvez ajouter ce lien profond à une page produit, telle que `dxdemo://exoticVibes`.

      4. Vous pouvez ajouter des boutons supplémentaires en appuyant sur **[!UICONTROL + Ajouter un bouton]**.

      5. Lorsqu’un second bouton est ajouté à votre message, vous avez désormais la possibilité de modifier la disposition du bouton à l’aide de la liste déroulante.


   2. **Formatage avancé**

      ![bouton de mise en forme avancée](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      L’activation de ce bouton donnera des options de personnalisation supplémentaires dans l’éditeur.

      1. Taille du média
      1. Police
      1. Taille du point
      1. Couleur de police
      1. Alignement

      ![options de formatage avancé](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **Onglet Paramètres**

      En passant à cet onglet et à la section **[!UICONTROL Aperçu]**, vous pouvez modifier l’**Aperçu de l’application**.
      <br>\
      ![Onglet Paramètres](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. La section **[!UICONTROL Mise en page]** vous donne la possibilité d’utiliser une image comme arrière-plan ou une couleur unie.

      2. La section **[!UICONTROL Message]** fournit des interactions personnalisées qui peuvent être activées pour votre message :
         1. Mouvements personnalisés
         2. Prise de contrôle de l’IU
         3. Prise de contrôle de l’interface utilisateur personnalisée
         4. Taille personnalisée
         5. Position personnalisée
         6. Animation personnalisée
         7. Coin arrondi du message
   <br>
4. Lorsque vous avez terminé de créer votre contenu et que vous êtes satisfait de votre message, cliquez sur le bouton **[!UICONTROL Vérifier pour activer]**.

   >[!SUCCESS]
   >
   > Vous avez maintenant terminé la création de votre message in-app mobile. Vous devriez maintenant être sur la page Campagne **[!UICONTROL Examiner pour activer]**.
   >
   >![vérifier et activer](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > Vous pourrez voir ici un résumé complet de votre message.
   >
   > *Notez la valeur personnalisée que vous avez utilisée comme règle de déclenchement. Cette valeur sera utilisée pour déclencher votre message in-app. La valeur utilisée se trouve dans la zone de mise en surbrillance de la page de résumé.*

   >[!NOTE]
   >Le déclencheur actuel du message in-app est le déclencheur par défaut **L’événement de lancement de l’application se produit**, ce qui signifie que le message in-app est déclenché lors du lancement de l’application. Voir à ce propos la section **[!UICONTROL Planification]**.

5. Si vous avez terminé de vérifier votre campagne, appuyez sur le bouton Activer pour publier la campagne.
   <br>
   ![activate](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> Vous devriez maintenant voir le tableau de bord Campagnes . Localisez votre campagne en faisant défiler l’écran ou en utilisant la fonction de recherche. Lorsque votre campagne passe au statut **[!UICONTROL En ligne]** (~1 min), votre campagne est maintenant publiée.
>
> ![Campagne publiée](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## Exercice 2.4 : déclencher le message in-app mobile

Pour actualiser la payload et télécharger la campagne que vous venez de publier :

1. Sur votre appareil mobile, fermez complètement l&#39;application Fréscopa.
2. Rouvrez l’application Fréscopa.
3. Accédez maintenant à l’onglet Exercice dans l’application.

   ![bouton Exercice](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. Dans le champ de texte, saisissez la valeur de déclencheur personnalisée que vous avez définie dans votre campagne. Appuyez ensuite sur Envoyer.


   ![modifier](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>En cliquant sur Envoyer, vous avez déclenché manuellement un déclencheur et la notification in-app que vous avez créée s’affiche :
>
>![&#x200B; Message in-app &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *Si vous rencontrez des problèmes lors du déclenchement de votre message, vérifiez les éléments suivants :*
> 
> * *Dans le champ Nom de l’événement de votre application mobile, veillez à saisir la valeur de votre règle de déclenchement de la même manière que dans Campaign.*
> * *Assurez-vous que les majuscules sont correctes et que vous n’avez pas d’espace de début ou de fin.*
> * *Vous pouvez rechercher la valeur de la règle de déclenchement que vous avez utilisée en revenant à la page de révision de la campagne en cliquant de nouveau sur votre campagne dans le tableau de bord de la campagne.*

Vous venez de créer et de publier votre premier message in-app Journey Optimizer.


## Exercice bonus : dupliquer la campagne et l’aperçu sur l’appareil

Les fonctionnalités **Dupliquer la campagne** et **Prévisualiser sur l’appareil** sont des fonctionnalités prêtes à l’emploi qui vous permettent de dupliquer vos campagnes, ainsi que de tester et de vérifier vos messages in-app directement sur votre appareil avant de l’activer. Dans cet exercice, vous apprendrez à utiliser cette fonctionnalité et à prévisualiser le message que vous avez créé dans l’exercice 3.1.

1. Ouvrez la campagne que vous venez de créer en cliquant sur son nom dans la page du tableau de bord des campagnes pour l’ouvrir. Vous revenez alors à la page **[!UICONTROL Vérifier la campagne]**.
1. Appuyez sur le bouton **[!UICONTROL Dupliquer]**. Une nouvelle invite s’ouvre alors pour nommer la nouvelle campagne en cours de duplication. Ajoutez un nouveau nom que vous mémoriserez facilement ou utilisez le nom par défaut où **[!DNL _copy]** est ajouté par défaut.

   ![dupliquer la campagne](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. Une fois que vous aurez appuyé sur le bouton Dupliquer, votre campagne en double sera créée et vous serez redirigé vers le tableau de bord des campagnes.
1. Une fois votre campagne dupliquée, ouvrez-la.

1. Vous pouvez accéder à la fonction Aperçu sur l’appareil sur la page **[!UICONTROL Révision de la campagne]** ou à l’étape **[!UICONTROL Auteur de la campagne]**.

   ![bouton Aperçu sur l’appareil](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. Cliquez ensuite sur le bouton **[!UICONTROL Démarrer]** dans l’écran de connexion à l’appareil.

   ![bouton démarrer](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Saisissez l’URL de base configurée pour lancer l’application Fréscopa : `dxdemo://`

   ![url de prévisualisation](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. Suivez les instructions à l’écran :
   1. Scannez le code QR avec votre appareil mobile et l’application Fréscopa s’ouvre avec un écran qui vous permet de saisir une épingle affichée.
   2. Saisissez l’épingle affichée dans AJO sur l’écran Assurance de votre appareil et cliquez sur le bouton Connexion qui s’affiche en bas à droite une fois que vous avez saisi l’épingle.


   ![saisir l’épingle](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. Ce pop-up s’affiche sur l’écran de votre ordinateur

   ![&#x200B; pop-up &#x200B;](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/3-3-pop-up.png)

1. Cliquez sur le bouton Terminé . La boîte de dialogue se ferme et votre téléphone est désormais connecté à l’aperçu sur l’appareil.


>[!SUCCESS]
>
> Votre message in-app apparaît sur votre appareil.
>
> *Une fois connecté, votre message in-app doit s’afficher à chaque fois, vous cliquez sur le bouton **[!UICONTROL Prévisualiser sur l’appareil]**.

## Ressources supplémentaires

**Vidéos pratiques :**

* [Créer une campagne in-app](/help/channels/create-an-in-app-campaign.md)
* [Créer un message in-app](/help/channels/author-in-app-messages.md)

**Documentation du produit :**

* [Prise en main du canal in-app](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/get-started-in-app)
* [Créer un message in-app mobile](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/create-in-app)
* [Concevoir votre contenu in-app](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/design-in-app)
* [Vérifier et envoyer votre notification in-app](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/in-app/send-in-app)
