---
title: "Le problème du Cocktail"
date: 2024-10-14
categories: 
  - "enigmes"
tags: 
  - "maths"
  - "optimisation"
coverImage: "pexels-photo-2531178-e1728932607974.webp"
draft: true
---

Ce problème peut être formulé en termes d'optimisation du trajet, en combinant la course à pied et la nage. L'idée de base est de comparer trois stratégies pour atteindre un point opposé sur le diamètre d'une piscine circulaire.

### Problème mathématique

Soit une piscine circulaire de rayon ( R ), avec un homme situé au point ( A ) (l'un des points du diamètre) cherchant à atteindre le point ( B ) (l'autre point du diamètre, opposé à ( A )). Il a trois options :

1. **Courir autour de la piscine** le long du périmètre.

3. **Nager directement à travers la piscine**, en suivant une ligne droite de ( A ) à ( B ).

5. **Courir sur une portion du périmètre** et plonger à un certain point pour nager en ligne droite vers ( B ).

Nous allons modéliser ce problème pour déterminer quelle option est la plus efficace.

### Variables

- Le rayon de la piscine est ( R ), donc le diamètre est ( 2R ).

- La vitesse de course est ( v\_c ) (mètres par seconde).

- La vitesse de nage est ( v\_n ) (mètres par seconde), avec ( v\_n < v\_c ) (on court généralement plus vite qu'on ne nage).

### Option 1 : Courir autour de la piscine

Le premier scénario consiste à courir le long du périmètre de la piscine. Le périmètre d'un cercle est donné par ( P = 2 \\pi R ). Le temps total nécessaire pour courir autour du périmètre est :

\[  
t\_{\\text{course}} = \\frac{2 \\pi R}{v\_c}  
\]

### Option 2 : Nager directement à travers la piscine

Dans ce scénario, l'homme plonge et nage directement à travers la piscine, en ligne droite, le long du diamètre ( AB ), qui mesure ( 2R ). Le temps total nécessaire pour nager ce diamètre est :

\[  
t\_{\\text{nage}} = \\frac{2R}{v\_n}  
\]

### Option 3 : Courir une portion et nager le reste

Le dernier scénario combine la course et la nage. L'homme court d'abord une distance ( x ) sur le périmètre, puis plonge et nage en ligne droite jusqu'au point ( B ).

1. La distance parcourue à pied le long du périmètre est ( x ), et le temps de course est :

\[  
t\_{\\text{course}} = \\frac{x}{v\_c}  
\]

2. Après avoir couru, l'homme plonge et nage en ligne droite. La distance de nage correspond à la longueur de la corde ( d ) qui relie le point d'entrée dans l'eau (situé à une distance angulaire ( \\theta ) du point ( A )) à ( B ), où ( \\theta ) est l'angle formé par la distance ( x ) avec le centre du cercle. Cette distance ( d ) est donnée par le théorème des cordes dans un cercle :

\[  
d = 2R \\sin\\left(\\frac{\\theta}{2}\\right)  
\]

Où ( \\theta = \\frac{x}{R} ) (puisque la distance ( x ) est mesurée sur le périmètre du cercle et que le périmètre total est ( 2 \\pi R )).

Le temps nécessaire pour nager cette distance est donc :

\[  
t\_{\\text{nage}} = \\frac{2R \\sin\\left(\\frac{x}{2R}\\right)}{v\_n}  
\]

Le temps total pour cette troisième option est donc la somme des deux temps :

\[  
t\_{\\text{total}} = \\frac{x}{v\_c} + \\frac{2R \\sin\\left(\\frac{x}{2R}\\right)}{v\_n}  
\]

### Comparaison des options

Pour savoir quelle option est la plus rapide, il faut comparer les temps obtenus dans chaque scénario. La meilleure stratégie dépendra des vitesses de course et de nage. En général :

- Si la vitesse de nage est beaucoup plus lente que la vitesse de course, il pourrait être plus efficace de courir une grande portion du périmètre avant de plonger.

- Si les vitesses sont similaires, nager directement ou courir autour pourrait être plus avantageux.

### Optimisation de la stratégie mixte

L'option 3 offre de la flexibilité, car le point où l'homme décide de plonger peut être optimisé. On peut minimiser le temps total ( t\_{\\text{total}} ) en prenant la dérivée par rapport à ( x ) et en cherchant le point où cette dérivée est nulle. Cela permet de trouver la meilleure distance ( x ) à courir avant de plonger.

### Conclusion

Ce problème de mathématiques est une belle illustration d'optimisation dans un contexte concret. La solution optimale dépend des vitesses relatives de la course et de la nage, et la stratégie mixte offre souvent la meilleure solution en fonction de ces paramètres.
