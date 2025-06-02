---
title: Création d’offres basées sur l’emplacement avec ciblage du code postal
description: Un élément d'offre dans la prise de décision représente un contenu personnalisé unique, tel qu'un message, une image, une promotion ou une recommandation, qui peut être diffusé à un utilisateur en fonction de règles et de conditions définies.
feature: Decisioning
role: User
level: Beginner
doc-type: Tutorial
last-substantial-update: 2025-05-30T00:00:00Z
jira: KT-18188
exl-id: 7dd49746-bea6-4679-9d88-d8f9d2aa5b52
source-git-commit: fb0ef6d502c6e3ba37ef528683a8888ed83f2990
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Création d’offres basées sur l’emplacement avec ciblage du code postal

Avant de créer les offres, le schéma Article de l’offre a été étendu afin d’inclure un nouveau champ : zipcode. Ce champ personnalisé permet de baliser explicitement chaque offre avec son code postal cible, ce qui permet le filtrage et le classement en fonction de l&#39;emplacement pendant la prise de décision.

Le schéma étant mis à jour, deux offres personnalisées ont été créées :

* Offre 1 : « Plans d’investissement flexibles pour Mira Mesa (92126) »
Conçue pour les jeunes professionnels et les résidents du 92126 qui privilégient les technologies, cette offre favorise des options d&#39;investissement flexibles telles que les FNB et les fonds communs de placement visant une croissance à long terme. Le champ code postal est défini sur 92126.

* Offre 2 : « CD à haut rendement pour Rancho Bernardo (92128) »
Ciblant les personnes financièrement stables et prêtes à prendre leur retraite en 92128, cette offre comprend des certificats de dépôt (CD) à haut rendement avec des rendements garantis. Le champ code postal est défini sur 92128.

Ces offres sont désormais enrichies de métadonnées d’emplacement, ce qui les rend éligibles à la sélection et au classement dynamiques en fonction des codes postaux des profils utilisateur aux étapes suivantes.

La capture d’écran suivante montre les attributs personnalisés ajoutés au schéma d’élément d’offre.

![offers-meta-data](assets/offers-meta-data.png)


## Offre pour 92126

Texte de l’offre pour les offres dans 92126 code postal

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #f9f9f9; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Boost Your Financial Game with Smart Investment Options   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     In Mira Mesa (92126), ambition meets opportunity. Whether you're building wealth or just getting started, our     <strong>diversified investment plans</strong> — including <strong>tech-focused ETFs</strong> and     <strong>flexible mutual funds</strong> — are designed to grow with your goals.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Enjoy expert guidance, low fees, and strategies built for busy professionals who want more from their money — without the hassle.   </p>   <a href="#start-investing" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Start Investing Smarter   </a> </div>
```


## Offre pour 92128

Texte de l’offre pour les offres dans 92128 code postal

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #fdfdfd; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">   <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">     Grow Your Savings with Confidence – Exclusive CD Rates for 92128   </h2>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Live in Rancho Bernardo? Take advantage of your financial momentum with our <strong>high-yield Certificates of Deposit</strong>, offering up to <strong>5.25% APY</strong>.     Designed for peace of mind and smart growth, our flexible CD options let you lock in guaranteed returns while enjoying the stability you deserve.   </p>   <p style="color: #333; font-size: 1rem; line-height: 1.6;">     Whether you're planning retirement or simply securing your future, this offer is tailored for residents like you.   </p>   <a href="#explore-cd-options" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">     Explore CD Options   </a> </div>
```

## Offre générique (offre de secours)

Texte de l’offre pour l’offre générique, sans code postal associé à l’offre

```html
<div style="max-width: 600px; margin: 2rem auto; padding: 1.5rem; border: 1px solid #ddd; border-radius: 12px; font-family: Arial, sans-serif; background-color: #ffffff; box-shadow: 0 4px 12px rgba(0,0,0,0.05);">
  <h2 style="color: #1a237e; font-size: 1.5rem; margin-bottom: 0.5rem;">
    Invest Smarter: Build Wealth with Flexible Financial Plans
  </h2>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Looking to take control of your financial future? Our flexible investment solutions are designed to meet a wide range of goals — from growing savings to planning for retirement.
    Choose from diversified mutual funds, ETFs, and professionally managed portfolios, all with expert guidance and minimal hassle.
  </p>
  <p style="color: #333; font-size: 1rem; line-height: 1.6;">
    Whether just starting out or optimizing an existing strategy, this offer provides the tools to invest with confidence — no matter where you live.
  </p>
  <a href="#explore-investment-plans" style="display: inline-block; margin-top: 1rem; background-color: #1a73e8; color: white; padding: 0.75rem 1.25rem; border-radius: 8px; text-decoration: none; font-weight: bold;">
    Explore Investment Plans
  </a>
</div>
```

Regroupez ces offres dans une collection appelée **offres liées aux revenus**

Les offres sont disponibles pour tous les visiteurs et visiteuses (il n’existe donc pas de contraintes d’éligibilité strictes). La formule de classement devient alors essentielle pour déterminer l’offre à afficher en fonction du contexte du profil.
Comme les règles d’éligibilité ne filtrent pas les offres, les trois sont traitées comme des candidats.
La stratégie de sélection récupère les trois.
La formule de classement les classe en fonction des attributs de profil (tels que le code postal et le revenu annuel) pour sélectionner le meilleur.
