---
title: "Cart Roulette"
date: 2024-10-14
categories: 
  - "enigmes"
tags: 
  - "e-commerce"
  - "maths"
  - "modelisation"
  - "probabilites"
draft: true
---

Dans le monde du e-commerce, l'achat compulsif est facilité par l'abondance de produits disponibles. Mais qu'en est-il si vous laissiez le hasard décider pour vous ? Imaginez que vous ayez 100 euros à dépenser et que vous décidiez d’acheter autant d’articles que possible sur un site de vente, mais avec une contrainte : le prix de chaque article est **aléatoire**. On se demande alors combien il vous restera d’argent après avoir effectué ces achats.

Ce scénario, que l’on pourrait appeler « **Cart Roulette** », nous invite à explorer une question intéressante liée aux probabilités et aux comportements aléatoires des dépenses. Dans cet article, nous allons décortiquer ce problème et comprendre ce qui se passe vraiment lorsqu’on laisse le hasard guider ses achats.

* * *

### Le principe de Cart Roulette

Voici le contexte du problème :

1. Vous disposez d’un budget initial de 100 euros.

3. À chaque tour, vous achetez le premier article que vous trouvez sur un site de vente.

5. Le prix de chaque article est déterminé aléatoirement.

7. Vous répétez cette opération autant de fois que vous le pouvez, jusqu’à ce que vous ne puissiez plus acheter d'article (soit parce qu'il ne vous reste plus assez d'argent pour acheter le prochain).

Le but est de déterminer **le reste d’argent** que vous aurez à la fin de cette série d’achats.

* * *

### Modélisation du problème

Pour modéliser ce problème, il faut prendre en compte plusieurs facteurs :

- **Prix aléatoire des articles** : Le prix de chaque article est tiré d'une distribution aléatoire. Ce type de distribution peut varier selon les hypothèses : les prix peuvent être uniformément répartis entre 1 et 100 euros, ou bien suivre une distribution plus complexe (comme une distribution normale, ou une distribution avec des produits majoritairement bon marché et quelques produits très chers).

- **Reste après chaque achat** : Après chaque achat, on soustrait le prix de l’article au budget restant. Le processus continue jusqu'à ce que le budget ne soit plus suffisant pour acheter un autre article.

* * *

### Le rôle de la distribution des prix

Le comportement de votre reste dépend en grande partie de la distribution des prix. Voici quelques scénarios types :

#### 1\. Distribution uniforme

Si les prix des articles sont uniformément répartis entre 1 et 100 euros, cela signifie que chaque prix a une probabilité égale d'être choisi. Dans ce cas, vous pourriez vous attendre à acheter environ 2 ou 3 articles (car en moyenne, les articles coûteront environ 50 euros chacun). Toutefois, vous pourriez parfois être chanceux et acheter des articles moins chers, ou au contraire, être confronté à des articles plus chers et ne pouvoir en acheter qu'un seul.

**Reste attendu** : Si la distribution est uniforme, on peut supposer qu'il vous restera en moyenne un montant assez faible (proche de 0), car vous risquez souvent de tomber sur des articles qui consomment une grande partie de votre budget dès les premiers tours.

#### 2\. Distribution normale centrée

Si les prix suivent une distribution normale centrée autour d’une valeur moyenne (disons 50 euros avec un écart-type de 10 euros), cela signifie que la majorité des prix seront proches de cette valeur, mais quelques-uns seront plus élevés ou plus bas. Ce type de distribution est plus réaliste pour les sites de vente où il y a une majorité de produits autour d’un prix moyen.

**Reste attendu** : Dans ce scénario, on pourrait s'attendre à ce que le nombre d'achats soit relativement constant (environ 2 articles) et le reste dépendra surtout des variations autour de cette moyenne.

#### 3\. Distribution biaisée (beaucoup de petits prix)

Imaginons maintenant une distribution où la majorité des articles sont peu chers (disons entre 1 et 20 euros) avec quelques produits beaucoup plus chers. Cela correspondrait à un site de vente où il y a beaucoup de petites babioles et quelques articles haut de gamme.

**Reste attendu** : Ici, vous pourrez probablement acheter un grand nombre de petits articles avant de tomber sur un produit plus cher qui arrêtera le processus. Le reste moyen sera souvent faible car le dernier article sera suffisamment cher pour laisser un budget résiduel très limité.

* * *

### Simulation du Cart Roulette

Pour mieux comprendre le phénomène, on peut envisager de simuler plusieurs séries d’achats aléatoires, en tirant des prix depuis une distribution donnée. Cela permettrait d’observer le comportement du reste d’argent après chaque simulation.

Voici quelques résultats que l'on pourrait obtenir selon la distribution des prix :

- **Uniforme** : Le reste moyen serait très proche de 0, car vous risquez d'épuiser votre budget rapidement avec des prix élevés.

- **Normale centrée** : Le reste d’argent moyen sera modéré, souvent autour de quelques euros, dépendant des variations dans les prix.

- **Distribution biaisée** : Le reste pourrait être plus élevé, car les petits prix vous permettent de réaliser plusieurs achats avant de tomber sur un produit plus cher qui vous laisse un petit montant non suffisant pour un achat supplémentaire.

* * *

### Conclusion : Que vous reste-t-il vraiment ?

Le problème de Cart Roulette est à la croisée de l’aléatoire et de la gestion de budget. Si le résultat dépend essentiellement de la distribution des prix, il reste intéressant de voir comment le hasard influence les dépenses et les achats en ligne.

**Conclusion générale** : Après une série d'achats aléatoires, il est probable qu'il vous reste très peu d'argent si les prix sont uniformément répartis ou suivent une distribution normale centrée. Toutefois, dans des scénarios où les petits prix dominent, vous pourriez finir avec un reste plus important et avoir acheté davantage d’articles.

Dans tous les cas, Cart Roulette nous rappelle l’importance de la chance lorsqu’il s’agit de gestion d'argent, et comment l’aléatoire peut parfois nous jouer des tours… ou des surprises !

* * *

Alors, la prochaine fois que vous naviguez sur un site de vente en ligne, résisterez-vous à l’appel du Cart Roulette ?
