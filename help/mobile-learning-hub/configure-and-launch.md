---
title: Configuration et lancement
description: Configurez les canaux mobiles dans Adobe Journey Optimizer (AJO) et Adobe Experience Platform (AEP), intégrez-les aux applications mobiles et assurez-vous d’être prêt pour l’exécution des campagnes marketing.
feature: Overview
role: Developer, Admin
level: Beginner, Intermediate
hide: true
index: false
last-substantial-update: 2025-08-22T00:00:00Z
exl-id: d8ffe406-b54b-455f-bd41-7d1fef0a4714
source-git-commit: 52f8a11ecec3553df42a28a1e1259cc70ba4fa30
workflow-type: tm+mt
source-wordcount: '2471'
ht-degree: 17%

---


# Configuration et lancement

Configurez les canaux mobiles dans Adobe Journey Optimizer et Adobe Experience Platform, intégrez-les aux applications mobiles et assurez-vous d’être prêt pour l’exécution de campagnes marketing.

>[!NOTE]
>
> Si vous découvrez Journey Optimizer et Experience Platform, familiarisez-vous avec les concepts de base en suivant ces cours :
>
> - [Configuration et administration de Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/courses/ajo-configure-and-administrate-ajo-environment)
>*Dans ce cours, vous apprendrez à configurer et à gérer l’environnement Journey Optimizer, y compris les rôles utilisateur, les autorisations, les sandbox et les canaux de messagerie, afin d’assurer des opérations efficaces et sécurisées.*
> - [Données d’ingénierie pour l’activation de Parcours intelligent dans Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/courses/ajo-engineer-data-for-intelligent-journey-activation)
>*Dans ce cours, vous apprendrez à configurer et à gérer des données de profil client en temps réel pour Journey Optimizer à l’aide d’Experience Platform. Maîtrisez la modélisation des données, le mappage d’identité et l’ingestion des données afin de créer des profils unifiés pour les parcours clients personnalisés.*


## Fonctionnalités mobiles dans Adobe Journey Optimizer

Découvrez les fonctionnalités mobiles que Adobe Journey Optimizer offre aux développeurs, aux spécialistes du marketing et aux équipes produit, notamment la messagerie push, la messagerie in-app et la personnalisation de contenu.

>[!VIDEO](https://video.tv.adobe.com/v/344615?captions=fre_fr&quality=12&learn=on){transcript=true}


## SDK mobile et configuration de l’application

Les implémentations mobiles dans Journey Optimizer commencent par l’intégration de **Adobe Experience Platform Mobile SDK** dans votre application. Les SDK sont essentiels à la collecte de données et à l’interaction avec Adobe Experience Platform (AEP) et ses applications, telles que Adobe Journey Optimizer (AJO).

Le SDK Mobile :

- Collecte les événements d&#39;application (vues d&#39;écran, appuis, achats, événements de cycle de vie, etc.) et les envoie à **Adobe Experience Platform Edge Network**.
- Gère l’**identité** et le **consentement** afin que Journey Optimizer puisse créer et utiliser en toute sécurité des profils client.
- Enregistre et met à jour **jetons push** et envoie **événements de tracking push et in-app** vers Adobe Experience Platform.
- S’intègre aux **extensions mobiles de Journey Optimizer** (push, in-app, cartes de contenu, prise de décision) afin que les messages puissent être diffusés, rendus et mesurés de bout en bout.

Sans Mobile SDK intégré à votre application, Journey Optimizer ne peut pas effectuer les opérations suivantes de manière fiable :

- Diffusez et suivez des messages push et in-app mobiles.
- Effectuez le rendu et le suivi des cartes de contenu.
- Utilisez le comportement in-app en temps réel pour déclencher des parcours et personnaliser les expériences.


>[!PREREQUISITES]
>
>Vérifiez que vous disposez des éléments suivants :
>
> - Adobe Journey Optimizer (AJO) est configuré pour votre organisation.
> - Accès à Adobe Experience Platform avec autorisations de collecte de données et de Journey Optimizer.
> - Droits d’administrateur dans AJO pour la configuration du canal et de la configuration.
> - Accès au code source de votre application mobile (iOS, Android ou framework multi-plateformes).
> - Les fonctionnalités requises au niveau du système d’exploitation sont activées pour votre application (par exemple, les autorisations push, les extensions du service de notification, les modes en arrière-plan).


### Composants Mobile SDK requis pour Journey Optimizer

Pour utiliser les canaux mobiles Journey Optimizer (notifications push, in-app, cartes de contenu, expériences basées sur du code), vous devez installer et configurer un ensemble d’extensions **principales** et **spécifiques au canal** dans votre application mobile :

>[!BEGINTABS]

>[!TAB Core]

#### Extensions principales (requises pour tous les cas d’utilisation mobile)

| Rôle | Exemples d’extensions (iOS/Android) | Remarques |
|----------------------|-----------------------------------------------|-------|
| Concentrateur d’événements et services | Mobile Core / AEP Core, AEP Services | Foundation pour toutes les autres extensions. Fournit un hub d’événements, une mise en réseau, un stockage et un état partagé. |
| Edge Network | Adobe Experience Platform Edge Network | Envoie les événements d’application à Adobe Experience Platform Edge Network. |
| Identité | Identité pour Edge Network | Gère l’ECID et les autres identités utilisées pour le profil et la segmentation. |
| Consentement | Consentement pour Edge Network | Collecte et applique les préférences de consentement de l’utilisateur. |
| Assurance | Assurance d’Adobe Experience Platform Assurance | Utilisé pour valider et déboguer la configuration de SDK et de canal de bout en bout. |

>[!TAB Spécifique au canal]

#### Extensions spécifiques aux canaux pour Journey Optimizer

| Canal/fonctionnalité | Extensions de clé supplémentaires (en plus du core) | Ce qu’ils activent |
|------------------------|---------------------------------------------------------------------|------------------|
| Notifications push | Extension mobile Journey Optimizer (push) | Enregistrez et mettez à jour les jetons push, envoyez des événements de suivi push et connectez-vous à la configuration push AJO. |
| Messagerie in-app | Extension mobile Journey Optimizer (in-app), composants de l’interface utilisateur de messagerie | Récupérez et affichez des messages in-app dans leur contexte, envoyez des impressions et des événements d’interaction. |
| Cartes de contenu | Messaging SDK avec prise en charge des cartes de contenu | Récupérez, générez et suivez des cartes de contenu pour des rapports Journey Optimizer précis. |
| Expériences basées sur du code | Extensions de Journey Optimizer/prise de décision ou API du serveur Edge | Récupérer des décisions pour des « surfaces » spécifiques dans votre application ; votre application contrôle la manière dont le contenu est rendu. |

>[!ENDTABS]

#### Propriété et configuration de balise mobile

Vous configurez ces extensions dans une **[propriété de balise mobile](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)** dans la collecte de données AEP (balises). Cette propriété contrôle :

- Les extensions Mobile SDK installées.
- Les événements de votre application qui déclenchent des appels vers Edge Network.
- La manière dont les données sont mappées dans XDM et transférées vers les solutions Adobe (Journey Optimizer, Analytics, etc.).

Vous pouvez créer et [configurer manuellement cette propriété mobile](https://experienceleague.adobe.com/fr/docs/platform-learn/data-collection/tags/create-a-property) ou, pour Mobile In-App et les notifications push, utiliser la **[Configuration guidée de canal](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** pour créer automatiquement la propriété de balise, le flux de données et la configuration de canal requis pour iOS et Android.

> **Conseil**\
> Pour les nouvelles mises en œuvre, **[Configuration guidée de canal](https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup)** est le point de départ recommandé. Il réduit le risque de flux de données mal configurés ou d’extensions manquantes et vous guide tout au long de la validation de SDK avec Assurance.

#### Prise en main de Mobile SDK :

<!-- CARDS
* https://experienceleague.adobe.com/fr/docs/platform-learn/data-collection/mobile-sdk/overview
    {description = Learn how Adobe Experience Platform Mobile SDK powers end-to-end engagement in your mobile applications.}
* https://experienceleague.adobe.com/fr/docs/platform-learn/implement-mobile-sdk/overview
* https://experienceleague.adobe.com/fr/docs/mobile
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/platform-learn/data-collection/mobile-sdk/overview" title="Présentation de Adobe Experience Platform Mobile SDK" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/33543?captions=fre_fr&format=jpeg&nocache=1763594622398" alt="Présentation de Adobe Experience Platform Mobile SDK"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        Présentation de Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/fr/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" title="Présentation de Adobe Experience Platform Mobile SDK"></a>
                    </p>
                    <p class="is-size-6">Découvrez comment Adobe Experience Platform Mobile SDK optimise l’engagement de bout en bout dans vos applications mobiles.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/platform-learn/data-collection/mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Implement Adobe Experience Cloud in mobile apps tutorial">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/platform-learn/implement-mobile-sdk/overview" title="Tutoriel sur l’implémentation de Adobe Experience Cloud dans les applications mobiles" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://experienceleague.adobe.com/fr/docs/platform-learn/implement-mobile-sdk/overview./media_1c75750ec1be623e56a379ca69ef6c495799e52a5.png?width=400&format=png&optimize=medium" alt="Tutoriel sur l’implémentation de Adobe Experience Cloud dans les applications mobiles"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" title="Tutoriel sur l’implémentation de Adobe Experience Cloud dans les applications mobiles">Tutoriel sur l’implémentation d’Adobe Experience Cloud dans les applications mobiles</a>
                    </p>
                    <p class="is-size-6">Découvrez comment implémenter les applications mobiles Adobe Experience Cloud. Ce tutoriel vous guide tout au long de l'implémentation des applications Experience Cloud dans un exemple d'application Swift ou Android.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/platform-learn/implement-mobile-sdk/overview" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">En savoir plus</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Adobe Experience Platform Mobile SDK Documentation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/mobile" title="Documentation SDK Mobile Adobe Experience Platform" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://cdn.experienceleague.adobe.com/thumb/exl-cards/documentation.png" alt="Documentation SDK Mobile Adobe Experience Platform"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/mobile" target="_blank" rel="referrer" title="Documentation SDK Mobile Adobe Experience Platform">Documentation Adobe Experience Platform Mobile SDK</a>
                    </p>
                    <p class="is-size-6">Recherchez des articles d’aide autonome et des tutoriels sur les SDK mobiles Experience Platform. Découvrez les stratégies et les bonnes pratiques des experts dans les événements vidéo en direct et à la demande.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/mobile" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">En savoir plus</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

Pour plus d’informations, consultez également la [documentation de Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/fr/docs/mobile)

#### Références du développeur :

- [Portail de développement de Mobile SDK (accueil)](https://developer.adobe.com/client-sdks/home/)
- [Versions actuelles de SDK](https://developer.adobe.com/client-sdks/home/current-sdk-versions/)
- [Prise en main d’une propriété mobile (balises)](https://developer.adobe.com/client-sdks/home/getting-started/create-a-mobile-property/)
- [Obtenir le SDK (l’installer dans votre application)](https://developer.adobe.com/client-sdks/home/getting-started/get-the-sdk/)
- [Suivi des événements avec Mobile SDK](https://developer.adobe.com/client-sdks/home/getting-started/track-events/)
- [Validation avec Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/)

>[!SUCCESS]
>
>**Liste de contrôle de préparation pour Mobile SDK**
>
> [ ] Core SDK installé (Core, Edge, Identity, Consent, Assurance).
> [ ] extensions mobiles Journey Optimizer ajoutées pour les canaux que vous utiliserez (push, in-app, cartes de contenu, code-based).
> [ ] Flux de données correctement configuré pour les jeux de données d’événement et de profil.
> [ ] Identité et consentement implémentés et validés avec Assurance.
> [ L’enregistrement et le suivi des jetons push ] sont validés de bout en bout.
> [ ] cartes in-app et/ou de contenu s’affichent validées sur un appareil.
> [ ] Configuration de canal guidé utilisée pour les nouvelles mises en œuvre ou configuration manuellement alignée sur les étapes documentées.



## Configuration du canal Adobe Journey Optimizer

### In-App, notifications push et WhatsApp

Configurez vos **canaux mobiles** à l’aide de la fonctionnalité de configuration de canal guidée. Comprendre comment configurer le canal **WhatsApp** :

<!-- CARDS
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup
 {description = Learn how to quickly set up and validate web and mobile channels across Experience Platform, Journey Optimizer, and Data Collection, and configure a push notification for a sample iOS marketing app.}
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Guided channel setup">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" title="Configuration guidée des canaux" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3449624/?captions=fre_fr&format=jpeg&nocache=1763594622823" alt="Configuration guidée des canaux"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" title="Configuration guidée des canaux">Configuration guidée des canaux</a>
                    </p>
                    <p class="is-size-6">Découvrez comment configurer et valider rapidement des canaux web et mobiles dans Experience Platform, Journey Optimizer et la collecte de données, et comment configurer une notification push pour un exemple d’application marketing iOS.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/web-and-mobile-channels/guided-channel-setup" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up the WhatsApp channel">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" title="Configurer le canal WhatsApp" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3470270/?captions=fre_fr&format=jpeg&nocache=1763594622814" alt="Configurer le canal WhatsApp"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" title="Configurer le canal WhatsApp">Configurer le canal WhatsApp</a>
                    </p>
                    <p class="is-size-6">Ce tutoriel explique comment configurer le canal WhatsApp dans Adobe Journey Optimizer pour permettre la diffusion de messages professionnels en temps réel.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/whatsapp-channel/set-up-whatsapp-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

### SMS/MMS/RCS

Configurez les **canaux SMS/MMS/RCS** avec les fournisseurs standard (Twilio, Synch ou Infobip) ou en utilisant un fournisseur de SMS personnalisé :

<!-- CARDS
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider
{description = Learn how to configure custom SMS providers in Journey Optimizer, set up API credentials and webhooks, manage opt-in/opt-out keywords, and launch personalized campaigns.}
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure SMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" title="Configurer des informations d’identification de l’API SMS et des surfaces de canal" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3418545?captions=fre_fr&format=jpeg&nocache=1763594624036" alt="Configurer des informations d’identification de l’API SMS et des surfaces de canal"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" title="Configurer des informations d’identification de l’API SMS et des surfaces de canal">Configurer les informations d’identification de l’API SMS et les surfaces des canaux</a>
                    </p>
                    <p class="is-size-6">Découvrez comment connecter Journey Optimizer à un fournisseur de services SMS et comment créer une surface de canal SMS.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-sms-channel" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure a custom SMS provider">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" title="Configurer un fournisseur de SMS personnalisé" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3431625/?format=jpeg&nocache=1763594624067" alt="Configurer un fournisseur de SMS personnalisé"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" title="Configurer un fournisseur de SMS personnalisé">Configurer un fournisseur SMS personnalisé</a>
                    </p>
                    <p class="is-size-6">Découvrez comment configurer des fournisseurs SMS personnalisés dans Journey Optimizer, configurer des informations d’identification d’API et des webhooks, gérer des mots-clés d’opt-in/opt-out et lancer des campagnes personnalisées.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-custom-sms-provider" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Configure MMS API credentials and channel surfaces">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" title="Configurer les informations d’identification de l’API MMS et des surfaces de canal" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3438048/?captions=fre_fr&format=jpeg&nocache=1763594624083" alt="Configurer les informations d’identification de l’API MMS et des surfaces de canal"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" title="Configurer les informations d’identification de l’API MMS et des surfaces de canal">Configurer les informations d’identification de l’API MMS et des surfaces des canaux</a>
                    </p>
                    <p class="is-size-6">Découvrez comment connecter Journey Optimizer à un prestataire de MMS et comment créer une surface de canal MMS.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/configure-mms-api-credentials-and-channel-surfaces" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Set up RCS in Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" title="Configurer des messages RCS dans Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3464757/?captions=fre_fr&format=jpeg&nocache=1763594624043" alt="Configurer des messages RCS dans Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" title="Configurer des messages RCS dans Journey Optimizer">Configurer des messages RCS dans Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Découvrez comment configurer et envoyer des messages RCS interactifs d’une marque dans Adobe Journey Optimizer à l’aide d’un fournisseur de SMS personnalisé. Ce tutoriel décrit comment configurer des informations d’identification d’API, des webhooks et des configurations de canal, puis créer un parcours pour diffuser des expériences de messagerie riches et personnalisées, le tout dans l’application de messagerie native.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/configuration/channel-configuration/sms-mms-channel/set-up-rcs" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Publications de blog

- [Utilisation de la personnalisation côté client (ODD) basée sur le réseau CDN sur mobile pour des personnalisations plus rapides.](https://experienceleaguecommunities.adobe.com/t5/journey-optimizer-blogs/using-cdn-based-client-side-personalization-odd-on-mobile-for/ba-p/761626?profile.language=fr)
- [Mobile Activation pour Adobe Experience Cloud](https://experienceleaguecommunities.adobe.com/t5/adobe-target-blogs/mobile-activation-for-adobe-experience-cloud/ba-p/541595?profile.language=fr)

## Garantissez la conformité aux lois sur la confidentialité et aux directives de la plateforme.

<!-- CARDS
* https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/privacy/privacy-landing-page{image=../mobile-learning-hub/assets/privacy.webp}{title = Privacy Features in Adobe Journey Optimizer}{description = Learn how to process privacy requests, audit user actions, manage consent, apply governance rules, and leverage advanced security options like Customer Managed Keys.}
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables{cta = Watch}
* https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Privacy Features in Adobe Journey Optimizer">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/privacy/privacy-landing-page" title="Fonctionnalités de confidentialité d’Adobe Journey Optimizer" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="../mobile-learning-hub/assets/privacy.webp" alt="Fonctionnalités de confidentialité d’Adobe Journey Optimizer"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" title="Fonctionnalités de confidentialité d’Adobe Journey Optimizer">Fonctionnalités de confidentialité de Adobe Journey Optimizer</a>
                    </p>
                    <p class="is-size-6">Découvrez comment traiter les demandes d’accès à des informations personnelles, auditer les actions des utilisateurs, gérer le consentement, appliquer les règles de gouvernance et exploiter les options de sécurité avancées telles que les clés gérées par le client.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/privacy/privacy-landing-page" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">En savoir plus</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Data Governance Framework Overview">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" title="Vue d’ensemble des cadres de gouvernance des données" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/33154/?captions=fre_fr&format=jpeg&nocache=1763594624934" alt="Vue d’ensemble des cadres de gouvernance des données"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" title="Vue d’ensemble des cadres de gouvernance des données">Vue d’ensemble du cadre de gouvernance des données</a>
                    </p>
                    <p class="is-size-6">Comprendre les fonctionnalités de gouvernance dans Adobe Experience Platform.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/data-governance-framework" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Classify data using labels">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" title="Classer les données à l’aide de libellés" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/3422795?captions=fre_fr&format=jpeg&nocache=1763594624932" alt="Classer les données à l’aide de libellés"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" title="Classer les données à l’aide de libellés">Classer les données à l’aide de libellés</a>
                    </p>
                    <p class="is-size-6">Découvrez comment étiqueter vos schémas et vos jeux de données.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/classify-data-using-lables" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Create Data Usage Policies">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" title="Créer des politiques d’utilisation des données" target="_blank" rel="referrer">
                        <img class="is-bordered-r-small" src="https://video.tv.adobe.com/v/37130/?captions=fre_fr&format=jpeg&nocache=1763594624933" alt="Créer des politiques d’utilisation des données"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" title="Créer des politiques d’utilisation des données">Créer des politiques d’utilisation des données</a>
                    </p>
                    <p class="is-size-6">Découvrez comment créer et gérer des politiques d’utilisation des données.</p>
                </div>
                <a href="https://experienceleague.adobe.com/fr/docs/journey-optimizer-learn/tutorials/data-governance-and-privacy/create-data-usage-policies" target="_blank" rel="referrer" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Regarder</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

## Pièges courants de mise en œuvre et moyens de les éviter

La plupart des problèmes mobiles trouvent leur origine dans la configuration de **SDK ou de la collecte de données**, et non dans les parcours ou les campagnes Journey Optimizer elles-mêmes. Utilisez le tableau ci-dessous pour identifier le problème, puis développez la section correspondante pour plus de détails.

### Pièges en un coup d’œil

| # | Problème/symptôme | Piège courant | Corriger en un coup d’œil |
|---|----------------------------------------------|-----------------------------------------------------|------------------------------------------|
| 1 | Échec de la configuration du canal guidé ; trafic faible ou nul | [versions ou extensions de SDK non alignées](#1-sdk-versions-and-extensions-not-aligned-with-channel-requirements) | Mettre à jour les versions de SDK/extension ; valider dans Assurance |
| 2 | Échec des lots de tracking ; erreurs dans AEP | [Flux de données ou jeux de données mal configurés](#2-misconfigured-datastreams-or-datasets) | Mapper des événements au jeu de données d’événement et des profils au jeu de données de profil |
| 3 | Les parcours ne se déclenchent pas ; personnalisation étrange | [Identité ou consentement manquant/incohérent](#3-missing-or-inconsistent-identity-and-consent) | Implémenter Edge Identity &amp; Consent ; vérifier dans Assurance |
| 4 | Aucune diffusion de notification push ou ouverture dans les rapports | [Enregistrement ou suivi du jeton push rompu](#4-push-token-registration-and-tracking-not-wired-correctly) | Correction de l’enregistrement des jetons et du suivi des interactions via SDK |
| 5 | Aucune impression in-app malgré les campagnes actives | [Les messages in-app ou les cartes de contenu ne s’affichent pas](#5-in-app-messages-or-content-cards-not-displaying) | Vérifier les extensions de message, les déclencheurs et les réponses de décision d’Assurance |

### Conseils détaillés par piège

Ouvrez le piège correspondant à vos symptômes pour savoir ce qu’il faut vérifier et comment le corriger.

<details id="1-sdk-versions-and-extensions-not-aligned-with-channel-requirements">
<summary><strong>1. Versions et extensions de SDK non alignées sur les exigences des canaux</strong></summary>

**Ce que vous remarquerez**

- Les activités push ou in-app n’atteignent pas l’appareil.
- Échec de la configuration du canal guidé ou de la validation du canal.
- Assurance présente les extensions Journey Optimizer, Edge ou Identity manquantes.

**Que vérifier**

- Utilisez-vous les versions d’extension minimales **Mobile Core** et **Journey Optimizer** requises par la configuration guidée de canal ?
- Dans **Assurance**, sous extensions et événements :
   - Les extensions attendues sont-elles chargées ?
   - Les événements sont-ils envoyés à Edge Network et confirmés ?

**Comment corriger**

- Effectuez la mise à niveau vers les versions d’extension Mobile SDK et Journey Optimizer prises en charge.
- Recréez l’application, reconnectez-vous à Assurance et réexécutez la configuration guidée du canal.

Voir : [Configurer les applications mobiles et web](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/configuration/guided-setup/set-mobile-config)

</details>


<details id="2-misconfigured-datastreams-or-datasets">
<summary><strong>2. Flux de données ou jeux de données mal configurés</strong></summary>

**Ce que vous remarquerez**

- Les événements ou les lots de suivi des notifications push échouent dans les jeux de données Platform.
- Erreurs d’ingestion de données (par exemple, « Les mises à jour ne sont pas prises en charge pour les événements »).
- Les rapports push ou in-app indiquent un suivi faible ou nul.

**Que vérifier**

- Quelqu’un a-t-il modifié les **schémas système ou jeux de données** créés pour le suivi Journey Optimizer ?
- Dans votre **flux de données** :
   - Les événements d’expérience sont-ils mappés à un **jeu de données d’événement** ?
   - Les attributs de profil sont-ils mappés à un **jeu de données de profil** ?

**Comment corriger**

- Ne modifiez pas les jeux de données/schémas système créés par AJO.
- Corrigez le mappage du flux de données (événements → jeu de données d’événement, profils → jeu de données de profil).
- Préférez la Configuration de canal guidée ou les étapes de flux de données documentées à des modifications ad hoc.

Voir : [Flux de notification push dans Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="3-missing-or-inconsistent-identity-and-consent">
<summary><strong>3. Identité et consentement manquants ou incohérents</strong></summary>

**Ce que vous remarquerez**

- Les parcours ne se déclenchent pas comme prévu pour les utilisateurs et utilisatrices de l’application.
- Personalization ne correspond pas au comportement de l’utilisateur dans d’autres canaux.
- Les événements apparaissent dans Experience Platform, mais les profils semblent fragmentés.

**Que vérifier**

- Le paramètre **Identité pour Edge Network** est-il implémenté et envoie-t-il un identifiant principal stable (par exemple, un identifiant de connexion) ?
- Le **consentement pour Edge Network** est-il implémenté et mis à jour lorsque les préférences changent ?
- Dans **Assurance** :
   - Les événements sortants incluent-ils des valeurs de consentement ?
   - Incluent-ils de manière cohérente l’ECID et vos identifiants principaux ?

**Comment corriger**

- Implémentez ou corrigez **Identity for Edge Network** dans l’application.
- Implémentez le **consentement pour Edge Network** et connectez-le à l’interface utilisateur de consentement de votre application.
- Testez à nouveau dans Assurance jusqu’à ce que l’identité et le consentement apparaissent sur tous les événements pertinents.

Voir : [&#x200B; Implémentation du consentement pour les implémentations de Platform Mobile SDK](https://experienceleague.adobe.com/fr/docs/platform-learn/implement-mobile-sdk/app-implementation/consent)

</details>


<details id="4-push-token-registration-and-tracking-not-wired-correctly">
<summary><strong>4. Enregistrement et suivi des jetons push non connectés correctement</strong></summary>

**Ce que vous remarquerez**

- Les utilisateurs ne reçoivent jamais de notifications push, même si des campagnes ou des parcours s’exécutent.
- Les rapports push n’affichent aucune ouverture, aucun rejet ni aucune interaction.

**Que vérifier**

- L’application enregistre-t-elle le jeton push avec l’extension Journey Optimizer :
   - Lors de la première installation ?
   - Après chaque mise à jour de l’application ?
   - Chaque fois que le système d’exploitation actualise le jeton ?
- Lorsque l’utilisateur ouvre ou ferme une notification, voyez-vous les événements de suivi dans Assurance ?

**Comment corriger**

- Ajoutez ou corrigez le code qui :
   - Enregistre le jeton via l’extension mobile Journey Optimizer à chaque fois qu’il est créé ou actualisé.
   - Envoie les événements d’interaction push (ouverture, ignorance, actions personnalisées) via Mobile SDK.
- Utilisez Assurance pour confirmer que les événements d’enregistrement et de suivi se déclenchent comme prévu.

Voir : [Flux de notification push dans Adobe Journey Optimizer](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/push/push-config/push-gs)

</details>


<details id="5-in-app-messages-or-content-cards-not-displaying">
<summary><strong>5. Les messages in-app ou les cartes de contenu ne s’affichent pas</strong></summary>

**Ce que vous remarquerez**

- Les messages in-app ou les cartes de contenu n’apparaissent jamais, malgré les campagnes ou les parcours actifs.
- Le compte rendu des performances affiche 0 impression.

**Que vérifier**

- L’extension **Journey Optimizer mobile messaging/in-app** et **Messaging SDK** sont-elles installées et enregistrées dans l’application ?
- Dans votre configuration **balises** :
   - Disposez-vous de règles qui déclenchent des requêtes sur les événements corrects (par exemple, les vues d’écran ou les événements personnalisés) ?
- Dans **Assurance** :
   - Lorsque ces événements se déclenchent, voyez-vous des demandes de décision in-app ou de carte de contenu sortir ?
   - Voyez-vous des réponses revenir d’Edge Network ?

**Comment corriger**

- Installer et enregistrer les extensions de messagerie requises
- Ajoutez ou corrigez des règles qui déclenchent des décisions sur vos événements cibles (écrans, événements personnalisés).
- Pour les cartes de contenu, assurez-vous des points suivants :
   - Récupérer des cartes via les API Messaging SDK.
   - Effectuez leur rendu dans l’interface utilisateur.
   - Suivre les interactions via le SDK.

Voir :
- [Créer et envoyer des messages in-app](https://experienceleague.adobe.com/fr/docs/platform-learn/implement-mobile-sdk/experience-cloud/journey-optimizer/journey-optimizer-inapp)
- [Configuration de la prise en charge des cartes de contenu dans Mobile SDK](https://experienceleague.adobe.com/fr/docs/journey-optimizer/using/channels/content-card/configure/content-card-lp)

</details>

>[!SUCCESS]
>
> **Liste de contrôle de préparation en une ligne**
>
> Avant de remettre l’application aux marketeurs, vérifiez dans **[Assurance](https://developer.adobe.com/client-sdks/home/base/assurance/)** que :
> 
> [ ] les extensions Core SDK + Journey Optimizer sont chargées,\
> [ ] événements circulent sur le flux de données et les jeux de données corrects,\
> [ ] L’identité et le consentement sont présents sur tous les événements clés,\
> [ ] jetons push et les interactions sont suivis, et\
> [ ] Au moins un message ou une carte de contenu de test in-app a été affiché et enregistré comme une impression.
