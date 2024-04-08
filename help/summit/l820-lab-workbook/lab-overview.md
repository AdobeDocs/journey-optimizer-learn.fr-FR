---
title: Classeur Lab - L820 - Créer des instants mobiles personnalisés avec Adobe Journey Optimizer
description: Explorez divers scénarios mobiles et apprenez à mettre en oeuvre des expériences personnalisées pour le web et les appareils mobiles avec Journey Optimizer.
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
source-git-commit: b4eb509d50afeea02eac937be85643aa22370249
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# CLASSEUR LAB

![Adobe Summit - texte de remplacement](/help/summit/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820 - Création de moments mobiles personnalisés avec Adobe Journey Optimizer

Dans ce laboratoire pratique, vous découvrez divers scénarios mobiles et apprenez à mettre en oeuvre des expériences personnalisées pour le web et les appareils mobiles avec Journey Optimizer.


>[!IMPORTANT]
>
>Veuillez vous abstenir de publier des photos ou des captures d&#39;écran de la session sur les médias sociaux.
><br>
>**Confidentialité des Adobes**
>Les informations et les divulgations de produits partagées aujourd&#39;hui au cours de ce laboratoire sont des informations confidentielles de l&#39;Adobe.
>Les participants ne peuvent reproduire, utiliser, diffuser ou divulguer des informations confidentielles à aucune personne ou entité.
>Les divulgations de produits sont faites à titre d’information uniquement, ne sont pas une garantie de fonctionnalités futures et peuvent être modifiées à tout moment. Par conséquent, ces fonctionnalités de produit ne font en aucun cas partie de votre accord avec Adobe ou de tout autre engagement envers vous.
><br>
>**Exclusion**
>Adobe vous permet d’accéder rapidement aux fonctionnalités qui exploitent la technologie d’IA générative. Veuillez noter que ces fonctionnalités sont encore en cours de développement et peuvent produire des réponses inattendues ou inexactes. Vos commentaires sont les bienvenus au fur et à mesure que cette fonctionnalité est mise sur le marché.


### Principaux points à retenir

* Découvrez la variété d’expériences mobiles prises en charge.
* Configurez une campagne push.
* Découvrez comment configurer des campagnes in-app mobiles.
* Configurez les messages web in-app.
* Testez vos propres scénarios personnalisés.

### Conditions préalables

* Connaissez votre numéro de siège : vous pouvez trouver votre numéro de siège sur le siège du poste de travail de la machine :

![Numéro de siège](/help/summit/l820-lab-workbook/assets/locate-seat-number.png)
Vous avez besoin d’un accès à :

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"}  - Les détails de connexion sont fournis pendant les exercices.
* [Site web de Fréscopa](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### Comprendre le cas d’utilisation

Fréscopa, une société dynamique et innovante, est spécialisée dans la transformation du café grâce à son mélange unique de services d&#39;abonnement à du café et d&#39;un large éventail de produits liés au café disponibles sur son site web et son application mobile. Avec l&#39;engagement de fournir une qualité et une saveur exceptionnelles, Fréscopa s&#39;adresse aux amateurs de café qui recherchent des options pratiques et de qualité supérieure.

Le coeur de l&#39;activité de Fréscopa est son service d&#39;abonnement à café, qui permet aux clients de bénéficier d&#39;un large choix de haricots de haute qualité livrés à leur porte. Cette approche personnalisée permet aux amateurs de café de profiter d&#39;une expérience fraîche et délicieuse, adaptée à leurs préférences.

Complémentant ses services d&#39;abonnement, le site web et l&#39;application mobile de Fréscopa propose une large gamme de produits liés au café, permettant aux clients d&#39;explorer et d&#39;enrichir leurs rituels de café. De l&#39;équipement de brasserie aux accessoires artisanaux, Fréscopa propose un guichet unique pour les amateurs de café qui recherchent la qualité et la commodité.

L’engagement de Fréscopa pour l’excellence s’étend au-delà de ses produits, car l’entreprise se consacre à la création d’un parcours client transparent et agréable. La combinaison de technologies innovantes et d’une approche axée sur le client place Fréscopa au premier plan de l’industrie du café en pleine évolution. Essentiellement, Fréscopa incarne la fusion de la passion et de la technologie, redéfinissant la façon dont les individus vivent et apprécient leur café. En mettant l&#39;accent sur la qualité, la commodité et les offres personnalisées, Fréscopa invite les amateurs de café à se lancer dans un parcours de saveur, livré directement à leur porte.
