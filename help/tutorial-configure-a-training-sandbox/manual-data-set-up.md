---
title: Configuration manuelle de la structure de données
description: Créez les espaces de noms d’identité requis et définissez la structure de données d’exemple Luma.
feature: Sandboxes, Data Management, Application Settings
doc-type: tutorial
kt: 9382
role: Admin
level: Beginner
hide: true
recommendations: noDisplay, noCatalog
exl-id: de870229-d9a6-4051-9f76-13d402cce3b4
source-git-commit: 4df1bdca81a585f728aa68519aa7ec7cd0c2f014
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 11%

---

# Configuration manuelle des données

Dans cette section, vous créez les espaces de noms d’identité requis et définissez les [!DNL Luma] exemple de structure de données en créant la variable [[!UICONTROL schémas]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=fr).

>[!TIP]
>Regardez le tutoriel vidéo [Mappage des identités](/help/set-up-data/map-identities.md) avant de commencer.

## Étape 1 : Création d’espaces de noms d’identité

Au cours de cette étape, vous créez des espaces de noms d’identité pour le [!DNL Luma] champs d’identité personnalisés nommés `lumaLoyaltyId`, `lumaCrmId`, et `lumaProductSKU`. Les espaces de noms d’identité jouent un rôle essentiel dans la création de profils clients en temps réel, car deux valeurs correspondantes dans le même espace de noms permettent à deux sources de données de former un graphique d’identités.

Commencez par créer un [!UICONTROL namespace] pour le [!DNL Luma Loyalty ID] schema :

1. Dans l’interface utilisateur de Journey Optimizer, accédez à **[!UICONTROL Client]** > **[!UICONTROL Identités]** dans le volet de navigation de gauche.

1. Sélectionner **[!UICONTROL Créer un espace de noms d’identité]**.

1. Indiquez les informations suivantes :

   | Nom d’affichage | Symbole d’identité | Type |
   |---|---|---|
   | `Luma Loyalty ID` | `lumaLoyaltyId` | [!UICONTROL Identifiant multi-appareils] |

1. Sélectionnez **[!UICONTROL Créer]**.

   ![Créer des espaces de noms](assets/createNamespace.png)

1. Créez deux espaces de noms supplémentaires en procédant de la même manière :

   | Nom d’affichage | Symbole d’identité | Type |
   |---|---|---|
   | `Luma CRM ID` | `lumaCrmId` | [!UICONTROL Identifiant multi-appareils] |
   | `Luma Product SKU` | `lumaProductSKU` | [!UICONTROL Identifiant de non-personne] |

## Étape 2 : Création de schémas

Au cours de cette étape, vous définissez la structure des données d’exemple en créant six [[!UICONTROL schémas]](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html?lang=fr):

* [[!DNL Luma Loyalty Schema]](#create-luma-loyalty-schema)

* [[!DNL Luma Product Catalog Schema]](#create-luma-product-catalog-schema)

* [[!DNL Luma Product Inventory Events] Schéma](#create-luma-product-inventory-event-schema)

* [[!DNL Luma CRM Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Web Events Schema]](#create-luma-crm-and-luma-product-interactions-schemas)

* [[!DNL Luma Offline Purchase Events Schema]](#create-additional-schemas)

* [[!DNL Luma Test Profiles Schema]](#create-additional-schemas)

>[!TIP]
>
>Regardez le tutoriel vidéo : [Création d’un schéma](/help/set-up-data/create-schema.md) avant de commencer.

### Créer [!DNL Luma Loyalty Schema] {#create-luma-loyalty-schema}

Cette section décrit comment créer le [!DNL Luma Loyalty] schéma et configuration des groupes de champs.

#### Création du schéma

1. Accédez à **[!UICONTROL GESTION DES DONNÉES]** > **[!UICONTROL Schémas]** dans le volet de navigation de gauche.

1. Sélectionner **[!UICONTROL Création d’un schéma]** en haut à droite.

1. Dans le menu déroulant, sélectionnez **[!UICONTROL XDM Individual Profile]**.

   Vous sélectionnez cette option car vous modélisez les attributs d’un client (points, statut, etc.).

#### Ajouter des groupes de champs existants

Vous êtes ensuite invité à ajouter des groupes de champs au schéma à l’aide de groupes. Vous devez ajouter des groupes de champs existants et créer un groupe de champs.

1. Sur le [!UICONTROL Schéma] , si le modal de groupes de champs ne s’ouvrait pas automatiquement, sélectionnez **[!UICONTROL Ajouter]**.

   ![Ajouter un groupe de champs](assets/add_field_group.png)

1. Sur le **[!UICONTROL Ajouter des groupes de champs]** , activez les groupes de champs suivants :

   * **[!UICONTROL Détails démographiques]** pour les données client de base telles que le nom et la date de naissance.

   * **[!UICONTROL Détails du contact personnel]** pour les détails de contact de base, tels que l’adresse électronique et le numéro de téléphone.

   * **[!UICONTROL Détails de fidélité]** pour les détails de fidélité, tels que les points, la date de jointure ou l’état. Le groupe de champs de fidélité est très bas dans la liste. Il est donc plus facile de le rechercher.

1. Sélectionner **[!UICONTROL Ajouter un groupe de champs]** pour ajouter les trois groupes de champs au schéma.

   ![Sélectionner des groupes de champs standard](assets/addstandardFieldGroups.png)

1. Sélectionnez le noeud supérieur du schéma.

1. Entrée `Luma Loyalty Schema` comme la propriété **[!UICONTROL Nom d’affichage]**.

#### Créez un [!UICONTROL groupe de champs] {#create-field-group}

Pour garantir la cohérence entre les schémas, Adobe recommande de gérer tous les identifiants système dans un seul groupe :

1. Dans la **[!UICONTROL Composition]** sous [!UICONTROL Groupes de champs], sélectionnez **[!UICONTROL Ajouter]**.

1. Sélectionner **[!UICONTROL Créer un groupe de champs]**.

1. Ajouter `Luma Identity Profile Field Group` comme la propriété **[!UICONTROL Nom d’affichage]**.

1. Ajouter `system identifiers for XDM Individual Profile class` comme la propriété **[!UICONTROL Description]**.

1. Sélectionnez **[!UICONTROL Ajouter des groupes de champs]**.

   ![Créer un groupe de champs](assets/addnewfieldgroup.png)

#### Ajouter des champs au nouveau [!UICONTROL groupe de champs]

Le nouveau groupe de champs vide est ajouté à votre schéma. Les boutons + vous permettent d’ajouter de nouveaux champs à n’importe quel emplacement de la hiérarchie. Dans ce cas, vous devez ajouter des champs au niveau racine :

1. Sélectionner **[!UICONTROL +]** en regard du nom du schéma.

   Cette étape permet d’ajouter un champ sous **votre identifiant de tenant** pour gérer les conflits entre vos champs personnalisés et tous les champs standard.

1. Dans le **[!UICONTROL Propriétés du champ]** dans la barre latérale, ajoutez les détails du nouveau champ :

   * **Nom du champ:** `systemIdentifier`

   * **[!UICONTROL Nom d’affichage] :**`System Identifier`

   * **Type :** Objet

   * **[!UICONTROL Attribuer un groupe de champs]:** [!DNL Luma identifiers]

1. Sélectionnez **[!UICONTROL Appliquer]**.

   ![Ajouter un identifiant de système](assets/addsysteidentifier.png)

   Ajoutez deux champs sous le `systemIdentifier` objet :

   | [!UICONTROL Fieldname] | [!UICONTROL Nom d’affichage] | [!UICONTROL Type] |
   |-------------|-----------|----------|
   | `loyaltyId` | `Loyalty Id` | [!UICONTROL Chaîne] |
   | `crmId` | `CRM Id` | [!UICONTROL Chaîne] |

![fields](./assets/add_fields.png)

#### Définition des identités

Vous disposez désormais de la variable [!UICONTROL namespace] et le [!DNL Luma Loyalty schema] configuré. Avant d’ingérer des données, vous devez libeller les champs d’identité. Chaque schéma utilisé avec [!UICONTROL Real-time Customer Profile] est requis pour qu’une identité Principale soit spécifiée et chaque enregistrement ingéré doit avoir une valeur pour ce champ.

1. Définissez la variable **Principale identité**:

   Dans la **[!DNL Luma Loyalty Schema]**:

   1. Sélectionnez la **[!DNL Luma Identity Profile Field Group]**.

   2. Sélectionnez la **[!DNL loyaltyId]** champ .

   3. Dans le **[!UICONTROL Propriétés du champ]**, activez la variable **[!UICONTROL Identité]** de la boîte.

   4. Activez la variable **[!UICONTROL Identité Principal]** de la boîte.

   5. Sélectionnez la `Luma Loyalty Id` namespace de **[!UICONTROL Espaces de noms d’identité]** menu déroulant.

   6. Sélectionnez **[!UICONTROL Appliquer]**.

      ![Principale identité](/help/tutorial-configure-a-training-sandbox/assets/primary_identity.png)

2. Définir une **identité secondaire**:

   Dans la **[!DNL Luma Loyalty Schema]**:

   1. Sélectionnez la **[!DNL Luma Identity Profile Field Group]**.

   2. Sélectionnez la `crmId` champ .

   3. Dans le **[!UICONTROL Propriétés du champ]**, activez la variable **[!UICONTROL Identité]** de la boîte.

   4. Sélectionnez la `Luma CRM Id` namespace de **[!UICONTROL Espaces de noms d’identité]** menu déroulant.

   5. Sélectionnez **[!UICONTROL Appliquer]**.

#### Activation pour le profil et enregistrement du schéma

1. Sélectionnez le noeud supérieur du schéma.

1. Dans le [!UICONTROL Propriétés du champ], activez **[!UICONTROL Profil]**.

   Le schéma doit se présenter comme suit :

   ![Schéma de fidélité Luma](assets/lumaloyaltyschema.png)

1. Sélectionnez **[!UICONTROL Enregistrer]**.

### Créer [!DNL Luma Product Catalog Schema] {#create-luma-product-catalog-schema}

1. Accédez à **[!UICONTROL GESTION DES DONNÉES]** > **[!UICONTROL Schémas]** dans le volet de navigation de gauche.

1. Sélectionner **[!UICONTROL Création d’un schéma]** (en haut à droite).

1. Pour créer une classe, sélectionnez **[!UICONTROL Parcourir tous les types de schéma]** dans le menu déroulant.

1. Sélectionner **[!UICONTROL Création d’une classe]**.

1. Ajoutez le nom d’affichage : `Luma Product Catalog Class`.

1. Attribuez une classe.

1. Créez un [!UICONTROL Groupe de champs]:

   * Nom d’affichage: `Luma Product Catalog Field Group`

1. Ajoutez le champ suivant au **[!DNL Luma Product Catalog Field Group]**.

   * Nom du champ: `product`

   * Nom d’affichage: `Product`

   * Type : [!UICONTROL Objet]

   * Groupe de champs: [!DNL Luma Product Catalog Field Group]

1. Sélectionnez **[!UICONTROL Appliquer]**.

1. Ajoutez les champs suivants au **[!DNL Product]** objet :

   | [!UICONTROL Fieldname] | [!UICONTROL Nom d’affichage] | [!UICONTROL Type] |
   |-------------|-----------|----------|
   | `sku` | `Product SKU` | [!UICONTROL Chaîne] |
   | `name` | `Product Name` | [!UICONTROL Chaîne] |
   | `category` | `Product Category` | [!UICONTROL Chaîne] |
   | `color` | `Product Color` | [!UICONTROL Chaîne] |
   | `size` | `Product Size` | [!UICONTROL Chaîne] |
   | `price` | `Product Price` | [!UICONTROL Double] |
   | `description` | `Product Description` | [!UICONTROL Chaîne] |
   | `imageURL` | `Product Image URL` | [!UICONTROL Chaîne] |
   | `stockQuantity` | `Product Stock Quantity` | [!UICONTROL Chaîne] |
   | `url` | `Product URL` | [!UICONTROL Chaîne] |

1. Définissez la variable **[!DNL SKU]** comme identité Principale.
1. Ajoutez la variable **[!UICONTROL Nom d’affichage]** `Luma Product Catalog Field Group` au [!UICONTROL groupe de champs].

1. Sélectionnez **[!UICONTROL Enregistrer]**.

### Créer [!DNL Luma Product Inventory Event Schema] {#create-luma-product-inventory-event-schema}

1. Accédez à **[!UICONTROL GESTION DES DONNÉES]** > **[!UICONTROL Schémas]** dans le volet de navigation de gauche.

1. Sélectionnez la **[!UICONTROL Création d’un schéma]** en haut à droite.

1. Dans le menu déroulant, sélectionnez **[!UICONTROL Parcourir tous les types de schéma]**.

1. Sélectionner **[!UICONTROL Création d’une classe]**.

1. Ajoutez le nom d’affichage : `Luma Business Event Class`.

1. Sélectionnez le type : *[!UICONTROL Série temporelle]*.

1. Attribuez une classe.

1. Créez un [!UICONTROL groupe de champs]:

   * Nom d’affichage: `Luma Product Inventory Event Details Field Group`

1. Ajoutez la variable **[!UICONTROL Nom d’affichage]** `Luma Product Inventory Event Schema` au schéma.

1. Ajoutez le champ suivant au **[!DNL Luma Product Inventory Event Details Field Group]**:

   * Nom du champ: `inventoryEvent`

   * Nom d’affichage: `Inventory Event`

   * Type : [!UICONTROL Objet]

   * Groupe de champs: `Luma Product Inventory Event Details Field Group`

1. Ajoutez les champs suivants au `Product Inventory Event Details` objet :

   | [!UICONTROL Fieldname] | [!UICONTROL Nom d’affichage] | [!UICONTROL Type] |
   |-------------|-----------|----------|
   | `sku` | `SKU` | [!UICONTROL Chaîne] |
   | `stockEventType` | `Stock Event Type` | [!UICONTROL Chaîne] |

   1. pour définir la variable `stockEventType` pour Enum, sélectionnez type : `string`.

   2. Faites défiler la page vers le bas de la page **[!UICONTROL Propriétés du champ]**.

   3. Activer **[!UICONTROL Enum]**.

   4. Entrée **[!UICONTROL values] ([!UICONTROL label)]**: `restock` (`Restock`).

   5. Sélectionner **[!UICONTROL Ajouter une ligne]**.

   6. Entrée **[!UICONTROL values] ([!UICONTROL label)]**: `outOfStock` (`Out of Stock`).

   7. Sélectionnez **[!UICONTROL Appliquer]**.

      ![enum](assets/enum.png)

1. Définir `inventory.Event.sku` champ comme **[!UICONTROL Principale identité]** en utilisant la variable **[!DNL LumaProductSKU namespace]**.

1. Sélectionnez la `sku` et définir une relation avec la propriété `product.sku` dans le champ **[!DNL Luma Product catalog Schema]** Schéma :

   1. Faites défiler la page vers le bas de la page **[!UICONTROL Propriétés du champ]**.

   2. Activer **[!UICONTROL Relation]**.

      1. **[!UICONTROL Schéma de référence]**: [!DNL Luma Product Catalog Schema].

      2. **[!UICONTROL Espace de noms d’identité de référence]**: [!DNL LumaProductSKU].
   3. Sélectionnez **[!UICONTROL Appliquer]**.

      Le schéma doit se présenter comme suit :

      ![Relation SKU](assets/sku_relationship.png)


1. Activer pour **Profil**.

1. Sélectionner [!UICONTROL Enregistrer] pour enregistrer le schéma.

### Création de schémas supplémentaires {#create-additional-schemas}

Créez les [!UICONTROL schémas]:

| [!UICONTROL Nom d’affichage] | [!DNL Luma CRM Schema] | [!DNL Luma Web Events Schema] | [!DNL Luma Test Profiles schema] | [!DNL Luma Offline Purchase Events Schema] |
|  ---| ------- | ---- |----|----|
| **[!UICONTROL Classe]** | [!UICONTROL XDM Individual Profile] | [!UICONTROL Événement d’expérience XDM] | [!UICONTROL XDM Individual Profile] | [UICONTROL XDM ExperienceEvent] |
| **[!UICONTROL Ajouter un groupe de champs existant]** | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details` | `Orchestration eventID`<br>`Consumer Experience Event`<br>`AEP Web SDK ExperienceEvent` | `Luma Identity Profile Field Group`<br>`Demographic Details`<br>`Personal Contact Details`<br>`Profile test details` | `Luma Identity Profile Field Group` <br>`Commerce Details` |
| **[!UICONTROL Relation]** |  | `productListItems.SKU`:<br> Schéma de référence `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |  | `productListItems.SKU`:<br> Schéma de référence `Luma Product Catalog Schema` <br>[!DNL Reference identity namespace] `lumaProductSKU` |
| **[!UICONTROL Identité Principal] [!UICONTROL namespace])** | `systemIdentifier.crmId` |  | `systemIdentifier.crmId` | `systemIdentifier.LoyaltyId` |
| **[!UICONTROL Activer pour le profil]** | oui | oui | oui | oui |

## Étapes suivantes

Maintenant que vous avez créé la structure de données, vous [créer des jeux de données et ingérer des exemples de données ;](/help/tutorial-configure-a-training-sandbox/manual-data-ingestion.md).
