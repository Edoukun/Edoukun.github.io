---
title: "Password cracking : le cas des code PIN"
date: 2024-10-15
categories: 
  - "enigmes"
  - "geek"
tags: 
  - "cybersecurity"
  - "hacking"
  - "statistiques"
draft: true
---

Dans cet article, nous allons explorer un sujet fascinant qui allie mathématiques et sécurité : l'analyse des **codes PIN** et leur fréquence d'utilisation. Inspiré par un post du blog DataGenetics qui s’intéresse aux **codes PIN les plus utilisés**, nous allons examiner les raisons derrière ces tendances et les implications de ces choix en matière de sécurité.

### Introduction : Les codes PIN et la sécurité

Un **code PIN** (Personal Identification Number) est une séquence de chiffres utilisée pour authentifier l’accès à des comptes bancaires, des téléphones, des cartes SIM, et bien plus encore. Avec seulement **10 000 combinaisons possibles** pour un code PIN à quatre chiffres (0000 à 9999), il semble que chaque combinaison devrait avoir une probabilité égale d’être choisie.

Cependant, en pratique, certaines combinaisons sont beaucoup plus courantes que d'autres. Cette préférence pour certains codes PIN provient de biais humains dans la manière de choisir ces séquences, ce qui a des conséquences directes sur la sécurité.

### Analyse des codes PIN les plus fréquents

Dans son analyse, DataGenetics a étudié une vaste base de données contenant des millions de codes PIN divulgués suite à des fuites de données. Les résultats montrent des tendances claires : certaines combinaisons sont extrêmement populaires, tandis que d'autres sont très rarement utilisées. Voici quelques faits marquants de l’analyse :

- **Le code PIN le plus courant est 1234**, utilisé par environ 10 % des utilisateurs. Ce résultat n’est pas surprenant : 1234 est simple, mémorable, et rapide à entrer.

- **Les 20 codes PIN les plus utilisés représentent près de 27 % de tous les codes choisis**, ce qui signifie qu'un quart des utilisateurs emploient une de ces combinaisons.

- **0000, 1111, 1212 et 9999** sont également des choix très populaires. La simplicité, la répétition de chiffres ou la symétrie sont souvent des facteurs qui rendent ces combinaisons plus attrayantes.

Voici un graphique des **20 PIN les plus fréquents** (d'après les données de DataGenetics) :

| Rang | PIN | Fréquence (%) |
| --- | --- | --- |
| 1 | 1234 | 10.71 |
| 2 | 1111 | 6.02 |
| 3 | 0000 | 1.88 |
| 4 | 1212 | 1.20 |
| 5 | 7777 | 0.75 |
| 6 | 1004 | 0.62 |
| 7 | 2000 | 0.61 |
| 8 | 4444 | 0.52 |
| 9 | 2222 | 0.50 |
| 10 | 6969 | 0.52 |

Ces chiffres montrent que **l’imprévisibilité** n’est pas vraiment au rendez-vous quand il s’agit de la sélection des codes PIN.

### Les biais humains dans le choix des PIN

L’une des raisons pour lesquelles certaines combinaisons sont plus fréquentes que d’autres est le **biais humain**. Nous avons tendance à choisir des séquences simples ou qui ont une signification particulière pour nous. Voici quelques-uns des principaux biais observés :

1. **Les séquences faciles à retenir** : Les séquences comme 1234, 0000 ou 1111 sont très populaires parce qu'elles sont simples à mémoriser et à taper. Cette commodité a cependant un coût élevé en termes de sécurité.

3. **Les dates de naissance ou anniversaires** : De nombreux utilisateurs choisissent des dates de naissance ou des années comme codes PIN, ce qui fait des combinaisons comme 1980, 1990 ou 2000 des choix assez fréquents. Les dates ajoutent une couche de prévisibilité car un attaquant pourrait connaître votre date de naissance via d’autres moyens (réseaux sociaux, par exemple).

5. **Les chiffres répétitifs ou symétriques** : Les séquences comme 1212 ou 6969 sont souvent choisies en raison de leur **symétrie** ou du fait qu'elles suivent un motif visuellement simple sur un clavier numérique.

7. **Les préférences culturelles** : Certaines combinaisons comme 7777 sont influencées par des connotations culturelles positives. Dans certaines cultures, le chiffre 7 est considéré comme chanceux, ce qui explique la popularité de combinaisons comme 7777.

### La sécurité des codes PIN : pourquoi cette popularité est un problème ?

Les résultats de cette analyse montrent un problème évident en termes de **sécurité**. Un attaquant qui veut deviner un code PIN n’a pas besoin d'essayer toutes les 10 000 combinaisons possibles. En se concentrant sur les 20 ou 50 codes PIN les plus fréquents, il augmente considérablement ses chances de réussite en un nombre limité d’essais. Si l’on considère que certaines cartes bancaires autorisent trois essais avant de bloquer la carte, cela donne un avantage significatif à l’attaquant.

Par exemple, si vous utilisez un code comme **1234**, un attaquant a déjà 1 chance sur 10 de deviner correctement votre code en un seul essai. Ces probabilités augmentent dramatiquement lorsqu’il essaie plusieurs combinaisons populaires.

### Comment améliorer la sécurité de son code PIN ?

L’analyse de DataGenetics révèle une leçon cruciale : pour renforcer la sécurité, il est essentiel de **choisir des combinaisons moins prévisibles**. Voici quelques conseils pour créer un code PIN plus sécurisé :

1. **Évitez les séquences évidentes** : Ne choisissez pas de codes simples comme 1234, 0000 ou 1111, même si ces combinaisons sont faciles à retenir.

3. **Évitez les dates de naissance** : Même si elles sont faciles à mémoriser, les dates de naissance sont trop prévisibles, surtout pour des personnes qui peuvent accéder à ces informations.

5. **Optez pour des combinaisons aléatoires** : Les codes aléatoires (comme 5836 ou 2917) sont beaucoup plus sûrs que les séquences ou motifs réguliers.

7. **Changez régulièrement votre PIN** : Il est recommandé de changer votre code PIN de manière régulière, surtout si vous pensez que votre ancien code a pu être compromis.

### Conclusion : La nécessité de la prudence

L’analyse des codes PIN montre que la sécurité des systèmes numériques dépend souvent de notre **comportement humain**. En choisissant des codes faciles à retenir, nous facilitons également le travail des attaquants. Cet article rappelle que, même dans des systèmes relativement simples comme les codes PIN, des principes de **randomisation** et de **sécurité** doivent être appliqués pour réduire les risques.

Ainsi, en apprenant à éviter les biais humains dans le choix de nos codes et en adoptant des pratiques plus sûres, nous pouvons rendre nos informations personnelles et nos comptes financiers beaucoup plus sécurisés.
