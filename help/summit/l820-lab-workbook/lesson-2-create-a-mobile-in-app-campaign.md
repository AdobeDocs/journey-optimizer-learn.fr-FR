---
title: Leçon 2 - Création d’une campagne in-app mobile
description: Créez et déclenchez une campagne in-app mobile.
feature: In App
role: User
level: Intermediate
doc-type: Article
duration: 0
recommendations: noDisplay, noCatalog
jira: KT-14983
thumbnail: KT-14983.jpeg
source-git-commit: c509c768d07984d07ed2ec65634e000c54bb6ff1
workflow-type: tm+mt
source-wordcount: '1395'
ht-degree: 0%

---


# Leçon 2 - Création d’une campagne in-app mobile

Dans cette leçon, vous créez et déclenchez des messages in-app mobiles.

## Objectifs d’apprentissage

* Comprendre comment les messages in-app sont déclenchés.
* Découvrez comment créer une campagne in-app mobile.
* Déclenchez un message in-app.

## Exercice 2.1 - Connexion à Journey Optimizer

1. Ouvrir [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}
2. Connectez-vous à l’aide des informations suivantes :
   <br>
   **Nom d’utilisateur :** L820+**`<your seat number>`**@adobeeventlab.com
   **Mot de passe :**   Adobe2024 !
   <br>
Vous pouvez trouver les détails de votre connexion sur votre ordinateur de bureau Lab. Utilisez Adobe ID et le mot de passe.
   ![bureau](/help/summit/l820-lab-workbook/assets/desk-top.png)

   ![Écran de connexion](/help/summit/l820-lab-workbook/assets/2-1-1-ajo-sign-in.png)
   <br>
3. Vous pouvez ignorer les deux écrans suivants :
   <br>
   ![Numéro de téléphone](/help/summit/l820-lab-workbook/assets/2-1-3-ajo-add-phone.png)
   <br>
   ![Fenêtre contextuelle de personnalisation](/help/summit/l820-lab-workbook/assets/2-1-4-ajo-personalization-pop-up.png)


>[!SUCCESS]
>
>Vous devez être connecté à Journey Optimizer et à la page d’accueil :
>
>![Page d’accueil AJO](/help/summit/l820-lab-workbook/assets/2-1-5-ajo-homepage.png)


## Exercice 2.2 Création d’une campagne in-app mobile

Dans cet exercice, vous créez une campagne de messagerie in-app, qui est déclenchée, lorsque vous ouvrez l’application.

1. Dans Journey Optimizer, dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Campagnes]**.

1. Cliquez sur **[!UICONTROL Créer une campagne]**.

   ![Créer une campagne](/help/summit/l820-lab-workbook/assets/2-3-1-1-create-campaign.png)

1. Sur le **[!UICONTROL Créer une campagne]** , dans la variable  **[!UICONTROL Action]** , sélectionnez **[!UICONTROL Message in-app]** .

1. Dans la **[!UICONTROL Envoyer à]** menu déroulant, sélectionnez **[!DNL Mobile]**.

1. Dans la **[!UICONTROL Surface de l’application]** menu déroulant, sélectionnez **[!DNL Frecopa Mobile App]**.

1. Cliquez sur **[!UICONTROL Créer]**.

   ![Surface de l’application](/help/summit/l820-lab-workbook/assets/3-1-1-1-create.png)

>[!SUCCESS]
>
>Vous devez maintenant vous trouver dans les propriétés de Campaign :
>
> ![Propriétés de la campagne](/help/summit/l820-lab-workbook/assets/3-1-1-2-campaign-properties.png)

## Exercice 2.3 Configuration de votre campagne

### 2.3.1 [!UICONTROL Section Propriétés]

Attribuez un nom à votre campagne. Veillez à commencer le nom par votre numéro de siège, afin que vous puissiez facilement retrouver votre campagne.

Par exemple, si le numéro de votre siège est 99 :  `99 - Welcome Campaign`.

![section propriétés](/help/summit/l820-lab-workbook/assets/3-1-2-1-properties-section.png)

### 2.3.2 Configuration de votre règle de déclenchement personnalisée

1. Faites défiler l’écran vers le bas jusqu’à **[!UICONTROL Section Triggers]**, puis cliquez sur **[!UICONTROL Modifier les déclencheurs]**.

   ![modify](/help/summit/l820-lab-workbook/assets/3-2-1-2-edit-triggers.png)

1. Dans le créateur de règles, cliquez sur **[!UICONTROL Lancement d’application]** et dans la liste déroulante  *Envoi de données à Platform*.
   ![Envoyé à la plateforme de données](/help/summit/l820-lab-workbook/assets/trigger-drop-down-sent-to-platform.png)

1. Ajoutez une condition en cliquant sur **[!UICONTROL Ajouter une condition]**.

   ![bouton d’ajout de condition](/help/summit/l820-lab-workbook/assets/3-2-1-3-add-condition.png)

1. Dans la **[!UICONTROL Sélection d’une caractéristique]** , sélectionnez **[!UICONTROL Type d’événement XDM]**.

   ![Type d’événement XDM](/help/summit/l820-lab-workbook/assets/4-1-2-dropdown-xdm-event.png)

1. Ajoutez un *`<custom string value>`* que vous pouvez vous souvenir.

1. Pour enregistrer la valeur, cliquez sur **[!UICONTROL Add**] `<custom string value>`.

   Cette valeur de chaîne personnalisée est utilisée ultérieurement pour déclencher votre message.

   >[!TIP]
   > L’ajout de votre numéro de siège à la valeur de chaîne personnalisée vous permet de vous souvenir plus facilement et de manière unique.
   > 
   > Par exemple : `99exerciseTrigger`

   ![ajouter une valeur de chaîne de déclencheur personnalisée](/help/summit/l820-lab-workbook/assets/3-1-2-2-add-custom-trigger.png)

1. Cliquez sur **[!UICONTROL Terminé]** en haut à droite.

>[!SUCCESS]
>
>Vous avez maintenant défini votre message in-app avec un événement déclencheur personnalisé.
>
>![Campagne avec déclencheur personnalisé défini](/help/summit/l820-lab-workbook/assets/3-1-2-2-campaign-with-custom-trigger.png)


### 2.3.3 Modification du contenu du message in-app

Dans le **[!UICONTROL Action]** , cliquez sur **[!UICONTROL Modifier le contenu]**.

![Bouton Modifier le contenu](/help/summit/l820-lab-workbook/assets/3-1-3-1-edit-content-button.png)

La variable [!UICONTROL Message In-App] s’affiche, où vous pouvez configurer le contenu du message in-app.

#### 2.3.3.1 Disposition

Sélectionnez la mise en page à appliquer à votre message.

Par exemple, cliquez sur **[!UICONTROL Modal]** pour faire de votre message in-app une disposition modale.

![bouton modal](/help/summit/l820-lab-workbook/assets/3-1-3-2-modal-button.png)

#### 2.3.3.2 Créer votre message et publier votre campagne

1. Dans la section multimédia, collez dans l’URL suivante :  `https://t3.ftcdn.net/jpg/02/79/42/52/240_F_279425217_Hr9VBkknMr4fTpuZbxZXfcYdC7jSvGl2.jpg`
   <br>
Lorsque vous cliquez en dehors du champ de valeur, votre image doit apparaître.

   ![média affiché dans l’aperçu](/help/summit/l820-lab-workbook/assets/3-1-3-2-media.png)

2. Dans la section **[!UICONTROL Contenu]** , ajoutez votre propre texte personnalisé que vous souhaitez afficher dans votre message pour le **[!UICONTROL En-tête]** et **[!UICONTROL Corps]**.

   ![En-tête et corps](/help/summit/l820-lab-workbook/assets/3-1-3-2-content.png)

3. Options supplémentaires :
   1. **Boutons :**

      ![Section Boutons](/help/summit/l820-lab-workbook/assets/3-1-3-2-buttons.png)

      1. Dans cette section de l’éditeur, vous pouvez personnaliser le texte de votre bouton CTA en modifiant le champ Texte du bouton .

      2. La variable **[!UICONTROL Événement Interact]** sert à définir la valeur transmise au SDK lorsque l’utilisateur appuie sur le CTA.

      3. La variable **[!UICONTROL Cible]** est utilisé pour définir l’emplacement où vous souhaitez que l’CTA emmène l’utilisateur. Cela inclut les URL et les liens profonds. Par exemple, vous pouvez ajouter ce lien profond à une page de produit telle que `dxdemo://exoticVibes`.

      4. Vous pouvez ajouter d’autres boutons en appuyant sur **[!UICONTROL Bouton Ajouter]**.

      5. Lorsqu&#39;un second bouton est ajouté à votre message, vous avez désormais la possibilité de modifier la disposition du bouton dans la liste déroulante.


   2. **Formatage avancé**

      ![bascule de mise en forme avancée](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-toggle.png)

      L’activation de ce bouton permet d’accéder à des options de personnalisation supplémentaires dans l’éditeur.

      1. Taille du média
      1. Police
      1. Taille de pt
      1. Police couleur
      1. Alignement

      ![options de mise en forme avancées](/help/summit/l820-lab-workbook/assets/3-1-3-2-advanced-formatting-options.png)

   3. **Onglet Paramètres**

      En passant sur cet onglet et dans **[!UICONTROL Aperçu]** , vous pouvez modifier la variable **Aperçu de l’application**.
      <br>\
      ![Onglet Paramètres](/help/summit/l820-lab-workbook/assets/3-1-3-1-settings-tab.png)
      <br>

      1. La variable **[!UICONTROL Disposition]** vous donne la possibilité d’utiliser une image comme arrière-plan ou couleur unie.

      2. La variable **[!UICONTROL Message]** fournit des interactions personnalisées qui peuvent être activées pour votre message :
         1. Mesures personnalisées
         2. Prise en main de l’interface utilisateur
         3. Prise en charge de l’interface utilisateur personnalisée
         4. Taille personnalisée
         5. Position personnalisée
         6. Animation personnalisée
         7. Coin rond du message
   <br>
4. Lorsque vous avez terminé de créer votre contenu et que vous êtes satisfait de votre message, cliquez sur le bouton **[!UICONTROL Réviser pour activer] button**.

   >[!SUCCESS]
   >
   > Vous avez maintenant terminé de créer votre message in-app mobile. Vous devriez maintenant être dans la campagne. **[!UICONTROL Réviser pour activer]** page.
   >
   >![révision et activation](/help/summit/l820-lab-workbook/assets/3-1-4-1-review-and-activate.png)
   >
   > Vous pourrez voir ici un résumé complet de votre message.
   >
   > *Prenez note de la valeur personnalisée que vous avez utilisée comme règle de déclenchement. Cette valeur sera utilisée pour déclencher votre message in-app. La valeur utilisée se trouve dans la zone de surbrillance de la page de résumé.*

   >[!NOTE]
   >Le déclencheur actuel du message in-app est la valeur par défaut. **Événement de lancement de l’application**, ce qui signifie que le message in-app est déclenché au lancement de l’application. Vous pouvez le voir dans la **[!UICONTROL Section Planning]**.

5. Si vous avez terminé de vérifier votre campagne, appuyez sur le bouton Activer pour publier la campagne.
   <br>
   ![activate](/help/summit/l820-lab-workbook/assets/3-1-4-2-activate.png)


>[!SUCCESS]
>
> Le tableau de bord Campagnes devrait maintenant s’afficher. Localisez votre campagne à l’aide du défilement ou de la fonction de recherche. Lorsque votre campagne passe à l’état **[!UICONTROL En direct]** (~1min), votre campagne a maintenant été publiée.
>
> ![Campagne publiée](/help/summit/l820-lab-workbook/assets/3-1-3-2-published-campaign.png)
>


## Exercice 2.4 Déclenchement du message in-app mobile

Pour actualiser la payload et télécharger votre nouvelle campagne publiée :

1. Sur votre appareil mobile, fermez complètement l’application Fréscopa.
2. Ouvrez à nouveau l’application Fréscopa.
3. Accédez maintenant à l’onglet Exercice de l’application.

   ![Bouton Exercice](/help/summit/l820-lab-workbook/assets/3-2-3-app-exercise-button.png)

4. Dans le champ de texte, saisissez la valeur de déclenchement personnalisée que vous avez définie dans votre campagne. Appuyez ensuite sur Envoyer.


   ![modify](/help/summit/l820-lab-workbook/assets/3-2-2-1-app-condition.PNG){width="250" align="center" zoomable="yes"}

>[!SUCCESS]
>
>En cliquant sur Envoyer, vous avez déclenché manuellement un déclencheur et la notification in-app que vous avez créée s’affiche :
>
>![Message in-app](/help/summit/l820-lab-workbook/assets/3-1-3-3-in-app-message.png)
>
> *Si vous rencontrez des problèmes lors du déclenchement de votre message, vérifiez les éléments suivants :*
> 
> * *Dans le champ Nom de l&#39;événement de votre application mobile, veillez à saisir la valeur de votre règle de déclenchement exactement comme vous l&#39;aviez dans Campaign.*
> * *Assurez-vous que la casse est correcte et que vous ne disposez pas d’un espace de début ou de fin.*
> * *Vous pouvez rechercher la valeur de la règle de déclenchement que vous avez utilisée si vous revenez à la page de révision de Campaign en cliquant de nouveau sur dans votre campagne dans le tableau de bord de Campaign.*

Vous venez de créer et de publier votre premier message in-app Journey Optimizer.


## Exercice bonus : duplication de campagne et aperçu sur appareil

La variable **Duplication d&#39;une campagne** et **Aperçu sur l’appareil** Les fonctionnalités sont des fonctionnalités prêtes à l’emploi qui vous permettent de dupliquer vos campagnes et de tester et de revoir vos messages In-App directement sur votre appareil avant de l’activer. Dans cet exercice, vous apprendrez à utiliser cette fonctionnalité et à prévisualiser le message que vous avez créé dans l’exercice 3.1.

1. Ouvrez l&#39;opération que vous venez de créer, en cliquant sur son nom dans le tableau de bord Campagnes pour l&#39;ouvrir. Cela vous ramène au **[!UICONTROL Campagne de révision]** page.
1. Appuyez sur la touche **[!UICONTROL Bouton Dupliquer]**. Une nouvelle invite s’affiche alors pour nommer la nouvelle campagne qui est dupliquée. Ajoutez un nouveau nom que vous mémorisez facilement ou utilisez le nom par défaut où **[!DNL _copy]** est ajouté par défaut.

   ![campagne en double](/help/summit/l820-lab-workbook/assets/3-2-duplicate-campaign.png)

1. Une fois que vous avez cliqué sur le bouton dupliquer , votre campagne en double est créée et vous êtes ramené au tableau de bord des campagnes.
1. Une fois la campagne dupliquée, ouvrez la nouvelle campagne.

1. Vous pouvez accéder à la fonction Aperçu sur le périphérique sur le **[!UICONTROL Examen des campagnes]** ou sur la page **[!UICONTROL Auteur de campagne]** étape .

   ![aperçu sur le bouton appareil](/help/summit/l820-lab-workbook/assets/3-3-1-1-preview-on-device-button.png)
   <br>

1. Cliquez ensuite sur le bouton **[!UICONTROL bouton de démarrage]** depuis l’écran de connexion à l’appareil.

   ![bouton de démarrage](/help/summit/l820-lab-workbook/assets/3-3-1-2-connect-to-device-start.png)
   <br>

1. Saisissez l’URL de base qui a été configurée pour lancer l’application Fréscopa : `dxdemo://`

   ![url d’aperçu](/help/summit/l820-lab-workbook/assets/3-3-1-3-preview-url.png)

   <br>

1. Suivez les instructions affichées à l’écran :
   1. Analysez le code QR avec votre appareil mobile, et l’application Fréscopa s’ouvre avec un écran qui vous permet de saisir une épingle affichée.
   2. Saisissez la épingle affichée dans AJO sur l’écran Assurance de votre périphérique et cliquez sur le bouton Se connecter qui s’affiche en bas à droite une fois que vous avez saisi la épingle.


   ![entrée pin](/help/summit/l820-lab-workbook/assets/3-3-1-5-enter-pin.PNG){width="250" align="center" zoomable="yes"}
   <br>
1. Cette fenêtre contextuelle s’affiche sur l’écran de votre ordinateur.

   ![pop-up](/help/summit/l820-lab-workbook/assets/3-3-pop-up.png)

1. Cliquez sur le bouton Terminé . La boîte de dialogue se ferme et votre téléphone est maintenant connecté à l’option Aperçu sur l’appareil.


>[!SUCCESS]
>
> Votre message in-app apparaît sur votre appareil.
>
> *Une fois connecté, votre message in-app doit s’afficher à chaque fois que vous cliquez sur le bouton **[!UICONTROL Aperçu sur l’appareil] button**.*