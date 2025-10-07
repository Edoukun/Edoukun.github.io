---
title: "Le Doomsday Algorithm, ou comment trouver le jour de la semaine pour n'importe quelle date"
date: 2024-10-14
categories: 
  - "enigmes"
  - "programmes"
tags: 
  - "algorithme"
  - "conway"
  - "maths"
  - "memoire"
coverImage: "IMG_5340-e1728933635829.png"
draft: true
---

Vous est-il déjà arrivé de vous demander quel jour de la semaine tombait un événement historique, comme la Révolution Française ou la première marche sur la Lune ? Ou encore, vous cherchez à savoir si une date d'anniversaire futur tombera un week-end ?

John Horton Conway, un mathématicien britannique célèbre pour son travail en théorie des jeux, a conçu un algorithme simple et efficace pour résoudre ce problème : l'algorithme **Doomsday**. Grâce à quelques étapes mentales, vous pouvez déterminer le jour de la semaine pour n'importe quelle date, même si elle remonte à des siècles ou qu'elle est loin dans le futur !

### La clé de l'algorithme : Le jour du "Doomsday"

Le principe central de l'algorithme est qu'il repose sur des **dates d'ancrage**, appelées **Doomsdays**, qui tombent le même jour de la semaine chaque année (ou presque). En connaissant le "Doomsday" d'une année donnée, vous pouvez calculer le jour de la semaine de n'importe quelle date cette année-là.

Voici quelques exemples de dates qui tombent toujours le même jour de la semaine chaque année :

- 4/4 (4 avril),

- 6/6 (6 juin),

- 8/8 (8 août),

- Halloween (31 octobre),

- Noël (24 décembre),

- Le dernier jour de février (28 février ou 29 février en année bissextile).

Ces jours sont tous alignés sur le **Doomsday** de l'année.

### Étapes de l'algorithme Doomsday

L'algorithme se décompose en quelques étapes simples pour déterminer le jour de la semaine associé à une date donnée.

#### Étape 1 : Calculer le Doomsday de l'année

Pour chaque année, le jour du Doomsday est calculé à partir d'un algorithme en quatre parties. Commençons par un exemple avec une année récente, comme **2023**.

1. **Les deux derniers chiffres de l'année** : Prenez les deux derniers chiffres de l'année. Pour 2023, c'est 23.

3. **Divisez par 12** : Divisez les deux derniers chiffres de l'année par 12 et gardez le quotient et le reste. Pour 23 :
    - Quotient : 23÷12=123÷12=1 (on garde le quotient),
    
    - Reste : 23−12=1123−12=11 (on garde aussi le reste).

5. **Divisez le reste par 4** : Prenez le reste (ici 11) et divisez-le par 4 en prenant uniquement le quotient (pas de reste cette fois). 11÷4=211÷4=2 (on garde le quotient).

7. **Sommez tout** : Additionnez le quotient de la division par 12, le reste, et le quotient de la division par 4. Pour 2023, cela donne 1+11+2=141+11+2=14.

9. **Réduire mod 7** : Prenez la somme et réduisez-la modulo 7, c'est-à-dire trouvez le reste de la division par 7. Pour 14, 14÷7=014÷7=0, donc le reste est 0.

Cela signifie que le Doomsday en 2023 tombe un **mardi**, car 0 correspond à un mardi selon la numérotation standard (dimanche = 0, lundi = 1, etc.).

#### Étape 2 : Repérer la date la plus proche sur le Doomsday

Ensuite, il faut trouver la date d'ancrage Doomsday la plus proche de la date que vous cherchez. Supposons que nous voulions déterminer quel jour était le **15 août 2023**.

1. Le 8 août (8/8) est un Doomsday.

3. Puisque nous savons que le Doomsday de 2023 est un mardi, cela signifie que le 8 août 2023 était un mardi.

5. Le 15 août est exactement une semaine plus tard, donc il tombe un **mardi également**.

#### Étape 3 : Ajuster pour les autres dates

Si la date que vous cherchez est éloignée d'un Doomsday, il suffit d'ajuster en ajoutant ou soustrayant des jours. Par exemple, si vous vouliez connaître le jour du **12 août 2023** :

- 8 août est un mardi,

- Le 12 août est quatre jours après, donc un **samedi**.

### Exemple plus complexe : 14 juillet 1789

Prenons maintenant une date historique célèbre, comme le 14 juillet 1789 (la prise de la Bastille). Comment utiliser l'algorithme pour cette date ?

1. **Doomsday de l'année 1789** :
    - Les deux derniers chiffres sont 89.
    
    - 89 divisé par 12 donne un quotient de 7 et un reste de 5.
    
    - Divisez 5 par 4 pour obtenir un quotient de 1.
    
    - Additionnez : 7+5+1=137+5+1=13.
    
    - Modulo 7 : 13÷7=613÷7=6, donc le Doomsday pour 1789 tombe un **samedi**.

3. Le dernier jour de février 1789 (28 février) tombe un samedi. Avançons jusqu'au 14 juillet :
    - Du 28 février au 14 juillet, il y a 136 jours.
    
    - 136 divisé par 7 donne 19 semaines complètes avec un reste de 3 jours.
    
    - Donc, 14 juillet 1789 était un **mardi**.

### Pourquoi appeler cet algorithme "Doomsday" ?

Le nom "Doomsday" (Jour du Jugement) est en réalité un clin d'œil amusant de Conway. Il a choisi ce terme pour illustrer l'idée que le Doomsday est un jour clé qui vous permet de "juger" ou de déterminer d'autres jours dans l'année. Rien de catastrophique, juste un outil pratique !

### Conclusion : Un outil puissant et amusant

Le Doomsday Algorithm est un excellent exemple de la façon dont la logique mathématique peut être appliquée à des tâches quotidiennes de manière rapide et efficace. Il montre également la beauté de la structure des calendriers et comment quelques règles simples peuvent nous aider à naviguer dans le temps.

Alors, la prochaine fois que vous vous demanderez quel jour de la semaine tombe une date spécifique, pas besoin d'un calendrier ! Utilisez l'algorithme Doomsday et épatez vos amis avec votre capacité à trouver rapidement la réponse.
