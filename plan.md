Architecture hexagonale
=======================

Problèmes
-----------------------

- Code framework qui polue le code métier
- Difficulté pour changer de framework
- Tests trop lourds (besoin de charger une BDD en mémoire, un framework de DI)

Début de projet
-----------------------

- Reporter les choix techniques
- Connaissance métier limitée en début de projet

Architecture en couches
-----------------------

- Simple à comprendre, montre le flux de données
- On n'a pas forcément une seule couche de présentation ni une seule couche de persistence
- L'isolation des couches est rarement garantie (entités dans la couche présentation par exemple)

Architecture héxagonale
-----------------------

- Permet d'isoler le code métier du code d'infrastructure
- Agnostique : vous pouvez l'utiliser avec votre langage préféré
- Anti-framework par excellence

Concept
-----------------------

- Code métier sans bibliothèque ni framework (ou alors très simples)
- Code technique dans des modules séparés

Un module de code métier et plusieurs modules techniques
Métier fournit les interfaces
Technique les implémente

Tests simplifiés
-----------------------

- Découpage des taches simplifié

Projets
-----------------------

- nouveaux : simple à mettre en place
- existants : beaucoup plus compliqué à déméller le spaggheti

Perspectives
-----------------------

- Besoin de changer de framework ? isolé dans un module
- Besoin de changer de BDD ? isolé dans un module
- Besoin de migrer une partie des données (ie SQL vers NoSQL) ? Module supplémentaire qui implémente les interfaces de l'ancien module


Points d'attention
-----------------------

- Archi qui permet de ne pas pouvoir utiliser du code "infra" dans le module métier, qui est au centre de tous les modules et permet ainsi l'isolation
- Rien n'empêche d'avoir du code métier qui se retrouve dans les modules "infra".
- Reste à départager ce qui est de l'infra de ce qui est du métier :
  - Des fois le métier pense trop à la forme des données en base et n'arrive pas à s'affranchir du stockage
  - Il faut pousser le métier déceler le vrai besoin dans sa demande (c'est pas le plus simple)
  - Faire des interface métier le plus simple possible et type au maximum la partie métier pour faire transiter les contraintes métier

Dans quels cas ne pas l'utiliser
-----------------------

- Développement d'un framework ou lib

Premier pas vers le DDD
-----------------------

- Avec des adapteurs clairement identifiés, on peut faire communiquer plusieurs héxagones, chacun représentant un métier séparé
- Un amateur pour faire une présentation du DDD ?