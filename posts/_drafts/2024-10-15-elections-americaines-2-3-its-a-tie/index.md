---
title: "Élections américaines (3/4) : It's a tie"
date: 2024-10-15
categories: 
  - "programmes"
  - "trivia"
tags: 
  - "algorithme"
  - "maths"
  - "politique"
draft: true
---

Les élections présidentielles américaines sont souvent des événements palpitants, et dans certains cas, elles peuvent devenir extrêmement complexes, notamment en raison du **Collège électoral**, un système qui détermine le président des États-Unis. Mais que se passerait-il si l'élection présidentielle aboutissait à une **égalité parfaite au sein du Collège électoral** ? Ce scénario rare et fascinant soulève des questions non seulement politiques, mais aussi **mathématiques**. Curieusement, ce problème d'égalité dans le Collège électoral peut être vu à travers le prisme d'un problème bien connu en théorie de la complexité algorithmique : le **problème de la somme de sous-ensembles**, un problème NP-complet.

Dans cet article, nous allons explorer comment une égalité dans le vote du Collège électoral pourrait être reliée au problème de la somme de sous-ensembles, et plus généralement à la théorie des problèmes NP-complets.

### Le Collège électoral et le risque d'égalité

Le système du Collège électoral aux États-Unis fonctionne de la manière suivante : chaque État dispose d’un certain nombre de grands électeurs, et ces électeurs sont attribués au candidat ayant remporté la majorité des votes dans cet État (dans la plupart des cas, selon le principe du "winner takes all"). Le candidat qui obtient **270 grands électeurs** ou plus (sur 538) remporte l’élection.

Cependant, que se passe-t-il si aucun candidat n’obtient ces 270 électeurs, c’est-à-dire si le vote du Collège électoral est **exactement de 269 à 269** ? Ce scénario, bien que rare, est mathématiquement possible et ouvre la porte à une série de délibérations complexes et de processus constitutionnels. En cas d'égalité, la décision de l'élection serait renvoyée à la Chambre des représentants, qui déciderait du vainqueur.

Mais avant d’arriver à cette étape politique, cette égalité parfaite au sein du Collège électoral peut être vue comme un problème mathématique qui ressemble à un casse-tête classique en algorithmique.

### Le lien avec le problème de la somme de sous-ensembles

L'égalité dans le Collège électoral peut être interprétée comme un problème mathématique de répartition. En effet, nous avons 538 électeurs à répartir en deux groupes égaux, représentant les deux candidats. C'est là que le lien avec le **problème de la somme de sous-ensembles** devient apparent.

#### Le problème de la somme de sous-ensembles (Subset Sum Problem)

Le problème de la somme de sous-ensembles est un problème bien connu en informatique théorique et appartient à la classe des problèmes **NP-complets**. Le problème se pose ainsi : étant donné un ensemble d'entiers, est-il possible de sélectionner un sous-ensemble de ces entiers dont la somme est égale à une valeur cible donnée ?

Formellement, étant donné un ensemble d'entiers ( S = {s\_1, s\_2, …, s\_n} ) et une valeur cible ( T ), le problème est de déterminer s'il existe un sous-ensemble de ( S ) dont la somme est exactement ( T ).

\[  
\\exists \\, S' \\subseteq S \\quad \\text{tel que} \\quad \\sum\_{s \\in S'} s = T ?  
\]

Le problème est difficile car il nécessite d'examiner toutes les combinaisons possibles des éléments de l’ensemble ( S ) pour vérifier si l'une d'entre elles satisfait la condition de somme exacte.

#### Le Collège électoral comme problème de somme de sous-ensembles

Imaginons maintenant que chaque État américain soit représenté par un nombre de grands électeurs (un nombre entier) et que nous cherchions à savoir s’il est possible de répartir ces électeurs en deux groupes ayant exactement le même total : 269 électeurs d'un côté, 269 de l'autre. Ce scénario est très similaire au problème de la somme de sous-ensembles.

Dans ce contexte :

- **L’ensemble des grands électeurs des États** est notre ensemble d’entiers ( S ).

- **La valeur cible ( T )** est 269, soit la moitié de la totalité des 538 électeurs.

- Le but est de savoir s'il est possible de diviser les États en deux groupes de taille égale en termes de grands électeurs.

Ce problème est non trivial car il exige d'explorer de nombreuses configurations possibles pour déterminer s'il existe une répartition qui mène à une égalité parfaite.

### Pourquoi ce problème est difficile : La nature NP-complète

Le problème de la somme de sous-ensembles est un problème **NP-complet**, ce qui signifie qu'il est au moins aussi difficile que n'importe quel autre problème NP, et qu’il est très probablement impossible de le résoudre de manière efficace (c'est-à-dire en temps polynomial) pour de grands ensembles de données.

Dans le cas du Collège électoral, cela revient à dire que la recherche d'une égalité exacte dans les votes électoraux est **computationnellement difficile**, même si, en théorie, une solution existe. Il faudrait explorer toutes les combinaisons possibles de regroupements d'États jusqu'à ce qu’on trouve, ou non, une configuration menant à une égalité parfaite.

Cette complexité illustre bien pourquoi une élection serrée et une égalité au sein du Collège électoral sont si rares et difficiles à anticiper. La nature NP-complète du problème rend impossible le calcul exact et prédictif à grande échelle, surtout lorsque l'on considère la diversité des tailles des États et l'évolution des votes d’une élection à l’autre.

### Les algorithmes et heuristiques pour les problèmes NP

Bien que les problèmes NP-complets soient difficiles à résoudre dans leur forme générale, il existe des **heuristiques** et des **algorithmes d’approximation** qui peuvent fournir des solutions suffisamment bonnes dans des situations pratiques.

Dans le cas du Collège électoral, des outils de simulation et des algorithmes pourraient être utilisés pour approcher le problème et tenter de déterminer les scénarios dans lesquels une égalité pourrait survenir. Cependant, ces approches ne garantissent pas une solution exacte, mais plutôt une estimation fondée sur des probabilités.

### Conclusion : Mathématiques et Politique, un lien inattendu

L’égalité parfaite dans le Collège électoral américain est un phénomène rare, mais sa modélisation mathématique révèle des connexions fascinantes avec des problèmes de complexité algorithmique comme le problème de la somme de sous-ensembles. Ce lien avec les problèmes NP-complets nous rappelle que certaines situations réelles, comme les élections, peuvent être incroyablement complexes à résoudre ou à anticiper.

Si une égalité parfaite devait se produire dans une élection présidentielle américaine, non seulement cela serait politiquement captivant, mais cela illustrerait également la manière dont des problèmes mathématiques profonds comme ceux de la théorie des ensembles et des algorithmes se manifestent dans la vie réelle.
