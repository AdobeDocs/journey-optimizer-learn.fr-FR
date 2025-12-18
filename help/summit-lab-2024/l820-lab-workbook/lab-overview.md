---
title: Lab Workbook - L820 - Création d’instants mobiles personnalisés avec Adobe Journey Optimizer
description: Explorez divers scénarios mobiles et apprenez à mettre en œuvre des expériences personnalisées pour le web et les appareils mobiles avec Journey Optimizer.
feature: Overview
role: User
level: Intermediate
doc-type: Tutorial
duration: 0
jira: KT-14977
thumbnail: KT-14977.jpeg
last-substantial-update: 2024-03-26T00:00:00Z
exl-id: e6d029f9-c936-427b-9d6e-4e296fd3c3ce
source-git-commit: 55ba1a46c1473d94847e7fccc69ed2a33badb54c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---

# CLASSEUR LAB

![Adobe Summit - texte secondaire](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/adobe-summit.png "Adobe Summit")

## L820 - Création d’instants mobiles personnalisés avec Adobe Journey Optimizer

Dans ce Lab pratique, vous explorez divers scénarios mobiles et apprenez à mettre en œuvre des expériences personnalisées pour le web et les appareils mobiles avec Journey Optimizer.


>[!IMPORTANT]
>
>Veuillez vous abstenir de publier des photos ou des captures d&#39;écran de la session sur les médias sociaux.
><br>
>**Confidentialité d’Adobe**
>Les informations et les produits divulgués aujourd’hui dans ce Lab sont des informations confidentielles d’Adobe.
>Les participants ne peuvent reproduire, utiliser, diffuser ou divulguer des informations confidentielles à aucune personne ou entité.
>Les divulgations de produits sont fournies à titre d’information uniquement, ne garantissent aucune fonctionnalité ou fonctionnalité future et peuvent faire l’objet de modifications à tout moment. Par conséquent, ces fonctionnalités de produit ne font en aucun cas partie de votre accord avec Adobe ou ne vous sont d&#39;aucune autre manière engagées.
><br>
>**Clause de non-responsabilité**
>Adobe vous permet d’accéder rapidement aux fonctionnalités qui exploitent la technologie d’IA générative. Veuillez noter que ces fonctionnalités sont toujours en cours de développement et peuvent produire des réponses inattendues ou inexactes. Vos commentaires sont les bienvenus lorsque nous commercialiserons cette fonctionnalité.


### Principaux points à retenir

* Découvrez la variété des expériences mobiles prises en charge.
* Configurez une campagne push.
* Découvrez comment configurer des campagnes in-app mobiles.
* Configurez les messages web in-app.
* Testez vos propres scénarios personnalisés.

### Conditions préalables

* Connaître votre numéro de poste : Vous pouvez trouver votre numéro de poste sur le bureau de la machine du laboratoire :

![Numéro de poste](/help/summit-labs/summit-lab-2024/l820-lab-workbook/assets/locate-seat-number.png)
Vous devez avoir accès à :

* [Adobe Journey Optimizer](https://experience.adobe.com/#/@techmarketingdemos/sname:summit-ajo-lab/journey-optimizer/home){target="_blank"} - les informations de connexion sont fournies pendant les exercices.
* [Site web de Fréscopa](https://dsn.adobe.com/p/adobe-summit-2024?token=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImFub255bW91cyIsImVtYWlsIjoiYW5vbnltb3VzQGFkb2JlLmNvbSIsImlzc3VlciI6InNoYXJlZC1saW5rIiwiYXJnb24iOnsiYWNjZXNzIjoicmVhZC1wcm9qZWN0IiwicHJvamVjdElkIjoiYWRvYmUtc3VtbWl0LTIwMjQifSwiaWF0IjoxNzEwNTI0MTIwLCJleHAiOjE3MTIzMzg1MjB9.q2uGVst6HjJw8SCWl-3pViNzepkdGnNCvGqZnbbkTsY){target="_blank"}


### Comprendre le cas d’utilisation

Fréscopa, une entreprise dynamique et innovante, se spécialise dans la révolution de l&#39;expérience café grâce à son mélange unique de services d&#39;abonnement au café et à une gamme diversifiée de produits liés au café disponibles sur son site web et son application mobile. Avec son engagement à offrir une qualité et une saveur exceptionnelles, Fréscopa s&#39;adresse aux amateurs de café à la recherche de commodité et d&#39;options de qualité supérieure.

Le cœur de l&#39;activité de Fréscopa réside dans ses services d&#39;abonnement au café, offrant aux clients une sélection de haricots de haute qualité livrés directement à leur porte. Cette approche personnalisée garantit aux amateurs de café de profiter d&#39;une expérience fraîche et délicieuse adaptée à leurs préférences.

En complément de ses services d&#39;abonnement, le site web et l&#39;application mobile de Fréscopa offrent une gamme complète de produits liés au café, permettant aux clients d&#39;explorer et d&#39;améliorer leurs rituels du café. De l&#39;équipement de brassage aux accessoires artisanaux, Fréscopa offre un guichet unique aux amateurs de café en quête de qualité et de commodité.

L&#39;engagement de Fréscopa envers l&#39;excellence va au-delà de ses produits, car la société se consacre à la création d&#39;un parcours client fluide et agréable. La combinaison de technologies innovantes et d&#39;une approche centrée sur le client positionne Fréscopa à l&#39;avant-garde de l&#39;industrie du café en pleine évolution. En substance, Fréscopa incarne la fusion de la passion et de la technologie, redéfinissant la façon dont les individus expérimentent et apprécient leur café. Axé sur la qualité, la commodité et l&#39;offre personnalisée, Fréscopa invite les amateurs de café à se lancer dans un parcours de saveurs, livré directement à leur porte.
