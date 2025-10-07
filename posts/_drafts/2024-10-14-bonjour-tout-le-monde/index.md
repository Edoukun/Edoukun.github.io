---
title: "Le problème de Josèphe"
date: 2024-10-14
categories: 
  - "enigmes"
  - "programmes"
tags: 
  - "enigme"
  - "maths"
coverImage: "Josephusbust-e1728932346916.jpg"
draft: true
---

Imaginez une partie de plouf-plouf macabre dans laquelle les perdants se feraient tuer. La légende que c'est à ce jeu mortel qu'a du jouer l'historien juif Flavius Josèphe pour sauver sa peau. Au Ier siècle, lors de la première guerre judéo-romaine, 40 de ses compagnons et lui se retrouvèrent encerclés par l'armée romaine. La majorité préférant mourir pluot que d être capturée, ils décidèrent donc d'un suicide collectif.

Ils convinrent de s'y prendre de la manière suivante : ils formeraient un cercle, et élimineraient chaque troisième personne jusqu'à ce qu'il n'en reste plus que deux. Les versions diffèrent pour dire s'il s'agissait de providence ou de manipulation, toujours est il que Josèphe en réchappa. Nous allons examiner quelques variantes de ce célèbre problème, en commençant par la plus simple :

**énigme de Josèphe** :

\[latexpage\] \\begin{tcolorbox}\[colframe=black,colback=white!10!white,sharp corners, boxrule=0.5mm\] \\textbf{Énigme de Josèphe :} On réunit N personnes autour d’une table. À partir d’un point de départ connu, et toutes les deux personnes, quelqu’un est éliminé. Le processus est répété jusqu’à ce qu’il n’en reste plus qu’un individu. Quelle place occupait cette personne au départ ? \\end{tcolorbox}

### Exploration des premiers cas

Bien que le processus soit assez simple au premier abord et facile à coder, sa solution est loin d'être immediate. Il est toujours de bon ton dans ce genre de situation de commencer avec quelques exemples simples pour essayer de discerner les subtilités de la mécanique générale.

Voici un widget d'animation qui vous permettra de visualiser quelques exemples N.

On définit J(N) :=

On aboutit donc aux valeurs suivantes :

Quelques remarques :

- les nombres pairs sont a eviter

- les puissances de 2 jouent un role

Notamment, on peut s'apercevoir que J(2 k) = 1. On peut montrer facilement par récurrence, que N = 2 k est une **condition suffisante** pour que J(N)=1.

Cas N =2

Heredite

Par commodité on pose J(1)=1

Pour tout n E N : J(2 k) = 1

### Résolution de l'énigme

Comme l'étape précédente nous y amène, le problème de Josephus peut être résolu de manière récursive. Si l'on connaît la position du survivant pour un cercle de _n-1_ personnes, on peut en déduire la position du survivant dans un cercle de _n_ personnes.

La solution mathématique s'exprime ainsi :

- Pour un seul participant, la solution est triviale : la position du survivant est 1.

- Pour plus de participants, si nous éliminons chaque _k_\-ième personne, la position du survivant pour _n_ personnes est donnée par la formule :

\[ J(n, k) = (J(n-1, k) + k) \\% n \]

où _J(n-1, k)_ est la position du survivant pour _n-1_ personnes, et _\\%_ est l'opérateur modulo, qui permet de gérer le retour au début du cercle.

Le problème de Josephus est un concept fascinant qui relie l'histoire ancienne aux mathématiques modernes. Ce problème, bien qu’il semble simple au premier abord, recèle une profondeur mathématique surprenante et offre des solutions élégantes à des défis complexes.

Inversion de Josephe. Il est preferable de se placer proche du 1er et impair.

### Le cas historique pour k = 3

Pour k=3. Le crible + visualisation.
