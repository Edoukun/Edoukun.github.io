---
title: "Dessine-moi un cylindre : une introduction aux VAE"
categories: 
  - "non-classe"
draft: true
---

Cet article s'inspire de l'excellent livre _Generative_ _Deep Learning_  de **David Foster**, qui propose une introduction accessible aux concepts fondamentaux de la modélisation générative. Plutôt que d'e viser'attaquer directement les modèles les plus avancés, comme les GAN ou les flux normaux, nous commencerons avec une première idée intuitive : les **Variational Autoencoders (VAE)**.

## **Principes Théoriques**

### Modélisation générative vs modélisation discriminante

Pour bien comprendre la modélisation générative, il est utile de la comparer à une notion connexe : la **modélisation discriminante**. Prenons l'exemple d’un algorithme de vision par ordinateur : supposons que nous lui présentions une image contenant potentiellement un cylindre. La tâche de cet algorithme discriminant est de classifier l'image : "contient-elle un cylindre ?".

À l’inverse, la **modélisation générative** ne se contente pas de reconnaître des motifs ; elle cherche à **apprendre à** **créer**.Dans notre exemple, un modèle génératif apprendrait à dessiner de nouveaux cylindres en capturant les propriétés sous-jacentes observées dans les données d’entraînement. En termes probabilistes, il vise à modéliser la distribution des données **P(X)**, alors que la modélisation discriminante se concentre sur les relations conditionnelles **P(y|X)**, où y représente les classes ou labels.

Cette distinction est cruciale : là où la modélisation discriminante catégorise les données, la modélisation générative tente d’en comprendre et d’en reproduire la structure sous-jacente. Cela ouvre des portes vers des applications fascinantes, comme la génération d’images, la création musicale, ou encore la synthèse vocale.

### Apprentissage par représentation

Pendant longtemps, les recherches en apprentissage automatique se sont surtout concentrées sur la modélisation discriminante, jugée plus simple et immédiatement applicable. Cependant, les progrès réalisés dans ce domaine ont également pavé la voie à la modélisation générative. Par exemple, les réseaux neuronaux convolutifs (CNN), initialement conçus pour classer ou détecter des objets, peuvent également être détournés pour générer de nouvelles données grâce à leur capacité à apprendre des **représentations riches**.

Mais qu'est-ce qu'une représentation ? Pour s'en donner une idée il est important de différencier  structures de données organisées et désorganisées. Dans notre exemple, une structure de données organisée pourrait consister en un tableau contenant directement des caractéristiques de l'image : nombre de segments, longueur de ces segments, volume contenu par la figure,...

Une image brute est loin de se présenter ainsi. Une telle structure est décrite par une collection de pixels identifiés par des coordonnées dont chacun pris isolément ne contient que très peu d’information. Pourtant, en assemblant ces pixels, nous percevons des formes, des textures, et des relations spatiales qui constituent l'information pertinent. Les réseaux neuronaux excellent à extraire automatiquement des caractéristiques pertinentes des structures désorganisées (comme les images) et à les réorganiser dans des **espaces où elles prennent du sens**. Cet espace, appelé **espace latent**, est une structure mathématique où les données brutes sont traduites en points reflétant leurs propriétés essentielles.

Dans notre exemple des cylindres, un espace latent bien construit pourrait représenter chaque cylindre par deux paramètres : sa hauteur et son rayon. Il s’agirait alors d’un espace à deux dimensions, ou plan, où chaque point correspond à un cylindre unique. Une fois cet espace défini, il devient possible de manipuler ou d'explorer les données en jouant directement sur leurs représentations latentes, comme générer des cylindres plus larges ou plus hauts.

Pour des données plus complexes, comme des visages, l’espace latent pourrait capturer des caractéristiques telles que la couleur des yeux, la forme du nez ou le type de coiffure. Cet espace serait alors beaucoup plus complexe, avec une dimensionnalité plus élevée que dans l’exemple des cylindres, mais toujours bien inférieure à celle des pixels bruts.

### Deep Learning

La puissance des réseaux de neurones repose sur deux grandes propriétés :

1. **Leur universalité** : les réseaux neuronaux peuvent approximer pratiquement toute fonction complexe, permettant ainsi de modéliser les relations entre données brutes et représentations abstraites.

3. **Leur scalabilité** : avec suffisamment de données et de puissance de calcul, ces modèles atteignent une précision impressionnante, même pour des tâches complexes.

Ces propriétés les rendent particulièrement adaptés à notre tâche de modélisation générative. Ce qui confère au **Deep Learning** son nom est double : d'une part, l’utilisation de couches successives qui permettent d’extraire progressivement des caractéristiques toujours plus abstraites ; d'autre part, la nature "boîte noire" des réseaux, où nous perdons le contrôle sur la manière exacte dont l'apprentissage se déroule.

Dans notre exemple des cylindres, nous avons une représentation intuitive basée sur des caractéristiques physiques comme le rayon et la hauteur, mais un réseau peut choisir d’apprendre une représentation complètement différente. Tant qu'elle permet de résoudre efficacement la tâche, nous n’avons aucun contrôle sur la manière dont les caractéristiques sont organisées ou extraites.

## **Auto-encoder simple**

### Schéma

Une manière intuitive d’aborder la modélisation générative est de créer une liaison directe entre un **espace latent** compact et les données originales. Autrement dit, on cherche à relier une structure de données désorganisée (comme une image brute) à une version condensée et plus informative qui résume ses propriétés principales. C'est précisément ce que fait un **autoencoder**.

L'autoencoder se compose de deux parties complémentaires :

1. **L'encodeur** : il mappe les données d'origine dans un espace latent, où les informations essentielles sont condensées en une représentation compacte.

3. **Le décodeur** : il reconstruit les données initiales à partir de cette représentation latente.

### Fonctionnement

Durant l'entraînement, l’autoencoder apprend à **compresser** et à **décompresser** efficacement les mêmes données. L'évaluation est réalisée via la minimisation de la perte de reconstruction qui mesure la différence entre l'image d'entrée et de sortie. Cela peut sembler être un simple exercice de compression sans utilité apparente, mais il recèle un potentiel génératif insoupçonné.

Pourquoi ? Parce qu’une fois le modèle entraîné, le **décodeur** devient un outil capable de **générer de nouvelles données**. Il suffit d’échantillonner des points dans l’espace latent (même aléatoirement) et de les passer dans le décodeur pour produire des exemples inédits. Ainsi, le décodeur constitue le cœur de la génération, tandis que l’encodeur sert principalement à **calibrer un espace latent structuré**.

### Mise en place d'un autoencoder

Pour illustrer le concept, nous allons travailler sur la génération de cylindres. Afin d’entraîner notre modèle, nous commencerons par construire un générateur qui produira un ensemble d’exemples de cylindres. Bien que cela puisse sembler artificiel (créer un générateur pour entraîner un autre générateur), la différence est importante : notre autoencodeur n’aura pas connaissance des règles utilisées pour construire ces exemples. Il devra apprendre à recréer des cylindres uniquement à partir des données observées. Ce processus met en évidence la capacité d’un autoencodeur à s’adapter à différents types de données, contrairement à notre générateur explicite qui ne pourra produire que des cylindres.

Vous pouvez consulter le code source utilisé pour ce projet. Voici quelques exemples de cylindres générés par notre modèle :

\[**Schéma des cylindres**\]

Les images produites sont volontairement simples : elles utilisent des niveaux binaires de noir et blanc et une résolution modeste de 64x64 pixels. Malgré cette simplicité, l’espace théorique des données reste extrêmement vaste : 2(64×64)). Pour relever ce défi, nous avons utilisé l’architecture suivante :

\[**Schéma ou description du réseau**\]

La perte de reconstruction utilisée est simplement l'entropie binaire croisée. Après un entraînement sur un ensemble de 1 000 cylindres pendant 50 epochs, nous avons échantillonné l’espace latent autour d’une grille pour visualiser les résultats produits par le décodeur :

\[**Exemples d’images générées**\]

Les cylindres générés au centre de la grille sont relativement convaincants, mais ceux situés en bordure commencent à perdre leur structure cylindrique. Pour mieux comprendre ce phénomène, nous avons représenté la répartition des données d’entraînement dans l’espace latent, qui est ici de dimension 2 :

\[**Graphique de l’espace latent**\]

Ce graphique montre que la structure apprise par l’encodeur est assez fragmentée : une grande partie de l’espace latent est vide ou mal utilisée. Cela s’explique par l’absence de contraintes explicites sur l’espace latent, hormis celle de permettre une reconstruction efficace des données d’entraînement. Rien ne garantit que cet espace soit continuellement décodable en cylindres cohérents.

Cette limitation est particulièrement visible ici : un "trou" apparaît entre deux groupes distincts de cylindres (par exemple, entre les cylindres de type I et ceux de type II). Si cette lacune est déjà perceptible en dimension 2, elle devient critique dans des espaces latents de dimension plus élevée. Un "trou" peut alors se transformer en véritable "crevasse", rendant l’échantillonnage aléatoire de nouveaux cylindres souvent invalide.

Pour remédier à ce problème et encourager une structure plus cohérente et continue de l’espace latent, les **Variational Autoencoders (VAE)** ont été conçus.

## **Variational Autoencoders (VAE)**

Les Variational Autoencoders s’appuient sur des concepts probabilistes pour créer un espace latent plus structuré et continu. Contrairement à un simple autoencodeur, un VAE considère la réduction en espace latent comme une distribution probabiliste, généralement gaussienne. Plus précisément, l’encodeur ne produit pas simplement un seul point dans l’espace latent, mais une distribution, typiquement représentée par une paire de variables aléatoires : la moyenne et la variance.

Lors de l’entraînement, cette distribution permet au modèle de réguler la densité des points dans l’espace latent afin de minimiser les "trous" ou les zones mal utilisées que nous avons vues précédemment. Le décodeur peut ensuite tirer parti de cette structure probabiliste pour générer des échantillons de manière plus réaliste et diversifiée.

Il est à noter que même si dans notre cas précis la distribution sous-jacente est uniforme, nous gardons davantage de bénéfices à conserver une distribution gaussienne. En effet, une distribution gaussienne permet une meilleure régularisation et une structure plus continue de l’espace latent, ce qui contribue à une génération de données plus stable et réaliste.

### Schéma du VAE

**\[Schéma du VAE\]**

Le schéma est similaire à celui d’un autoencodeur, à la différence près que cette fois les données d'entraînement sont contraintes à être régulées dans l’espace latent de sorte à limiter les risques de fragmentation ou d’incohérences.

### Fonctionnement

Pour y parvenir, l’évaluation durant l’entraînement est réalisée via la minimisation d’une perte composite constituée de :

- **La perte de reconstruction** : qui évalue la qualité des données générées, comme pour un autoencodeur simple

- **La perte KL** (ou divergence de Kullback-Leibler) mesure la différence entre la distribution latente approximée par l’encodeur et la distribution gaussienne

En ajustant le poids de la perte KL par rapport à la perte de reconstruction, on peut équilibrer la régularisation du réseau afin de maintenir une qualité de reconstruction suffisante tout en améliorant la structure de l’espace latent.

### Mise en place d'un VAE

Voici l’architecture retenue :

\[Schema\]

La difference est vue sur l espace latent.

Après un entraînement sur un ensemble de 1 000 cylindres pendant 50 epochs, nous avons échantillonné l’espace latent autour d’une grille pour visualiser les résultats produits par le décodeur :

\[Schema\]

Nous pouvons observer une distribution plus homogène dans l’espace latent, avec une meilleure dispersion autour des différentes classes de cylindres. Cela signifie que les générateurs peuvent produire des variations continuellement intéressantes et toujours proches de ce que nous attendons d’un cylindre réaliste.

Graphique de l’espace latent :

\[**Graphique de l’espace latent**\]

L’un des principaux avantages des Variational Autoencoders est leur capacité à générer des données variées tout en maintenant une qualité constante. Cela permet une exploration beaucoup plus fluide et naturelle de l’espace latent, où chaque point correspond à une variation contrôlée et réaliste des données initiales. Ainsi, si nous prenons deux cylindres aléatoires, nous pouvons réaliser un "morphing continu" de l'un à l'autre :

\[Schema\]

## **Développements**

### Ajout d'une dimension

### Généralisation à d'autres figures

Création de la sphère cylindrique

## **Conclusion**
