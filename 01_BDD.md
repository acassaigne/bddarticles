= Intéret BDD

Ce premier article inaugure une serie ayant pour thématique le  Behaviour
Driven Development (BDD). Pourquoi s'intéressé au BDD ? Le BDD offre de
nombreux intérêts, premièrement il est un moyen de spécification basé sur des
exemples clés levant ainsi bon nombre d'ambiguïtés. Utiliser pleinement
l'approche BDD c'est également implémenter ces tests d'acceptances via un eco-système 
outils existant.  

Pourquoi vouloir implémenter ces tests d'acceptances ?

- C'est ici qu'un double bénéfice se dégage, le premier est la
cristallisation de la connaissance métier au sein de scénarii écrits et çà représente une documentation vivante du fonctionnement de votre système. 
- Le second bénéfice est que ça offre à l'équipe de développement un filer de sécurité non négligeable limitant ainsi les risques régressions.
- Autre effet positif, aller jusqu'a l'implémentation pousse et imposse un meilleur formalisme des tests d'acceptance. 

Nous développons cette article autour d'un projet portant sur le développement d'un logiciel dans le domaine de la logistique.
Nous entreprise souhaite développer un système de gestion de stock et de préparation des commandes. Les commandes arrivent bien évidement d'un système amont soit de type commerce en ligne soit directement par les commerciaux de l'entreprise. L'équipe de développement à la responsabilité de la réalisation du système aval prenant en charge la préparation des commandes et la gestion des stocks.

L'équipe a décidé d'adopter une approche agile et est doté d'un product owner dénomé Mathieu. Notre product owner Mathieu a priorisé les User Stories ayant le plus de valeur. Parmis celles-ci la plus importante selon Mathieu est la User Story suivante :
Afin de pouvoir livrer la commande de mon client.
Je peux déclencher la préparation d'une commande. 
En tant que Damien (préparateur).

Après quelques échange autour de cette user story, les tests d'acceptances suivants ont émergés :
Etant donné la commande 111 
composé d'un T-shirt bleu (référence produit P455677) 
et d'un stock P455677 de 3 produits.
Alors lorsque je déclenche la préparation de la commande 111
Then le stock P455677 est de 2 produits.
 et le n° de préparation est AAAAMMDD-111

Test n°2

Plus de stock

Test n°3 avoir le bon livraison avec les produits.


Les exemples métier sont la matiere premiére des tests que nous implémenterons

Ces exemples sont 
Il permet d'établir un
scope plus claire aux User Stories en établissant les tests acceptance

Tests acceptance,
BDD,

