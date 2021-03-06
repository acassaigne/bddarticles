= Intéret BDD

Ce premier article inaugure une serie ayant pour thématique le  Behaviour
Driven Development (BDD). Pourquoi s'intéressé au BDD ? Le BDD offre de
nombreux intérêts, premièrement il est un moyen de spécification basé sur des
exemples clés levant ainsi bon nombre d'ambiguïtés. Utiliser pleinement
l'approche BDD c'est également implémenter ces tests d'acceptances via un eco-système 
outils existant.  

Pourquoi vouloir implémenter ces tests d'acceptances ?
Car nous pouvons en tirer les bénéfices suivants :

- Le premier est la cristallisation de la connaissance métier au sein de scénarii écrits.
- L'écriture de scénarii représentent alors une documentation vivante du fonctionnement de votre système. 
- Le second bénéfice est que ça offre à l'équipe de développement un filer de sécurité non négligeable limitant ainsi les risques régressions.
- Autre effet positif, aller jusqu'a l'implémentation pousse et imposse un meilleur formalisme des tests d'acceptance. 

Nous développerons cette série article autour d'un projet portant sur le développement d'un logiciel dans le domaine de la logistique.
L'entreprise de logistique souhaite développer un système de gestion de stock et de préparation des commandes. Les commandes arrivent évidement d'un système amont pré-éxistant de type commerce en ligne. L'équipe de développement à la responsabilité de la réalisation du système aval prenant en charge la préparation des commandes et la gestion des stocks.

L'équipe a décidé d'adopter une approche agile et est doté d'un product owner dénomé Mathieu. Notre product owner Mathieu a priorisé les User Stories ayant le plus de valeur. Parmis celles-ci la plus importante selon Mathieu est la User Story suivante :
Afin de pouvoir livrer la commande de mon client.
Je peux déclencher la préparation d'une commande. 
En tant que Damien (préparateur).

Après quelques échanges réalisés au sein de l'équipe avec le product owner,
un premier scénario constituant un test d'acceptance pourrait être le suivant :

Etant donné que la commande A20150707001 comporte 1 produit commandé dont la référence est 9782940199617
Etant donné que le stock du produit 9782940199617 est de 3 
Quand je déclenche la préparation de la commande A20150707001
Alors j'obtiens ce n° de préparation AAAAMMDD-111
Alors le stock du produit 9782940199617 est de 2

Test n°2

Etant donné que la commande A20150707001 comporte 1 produit commandé dont la référence est 9755566899605
Etant donné que le stock du produit 9755566899605 est de 0 
Quand je déclenche la préparation de la commande A20150707001
Alors j'obtiens l'erreur pas assez de stock
Alors le stock du produit 9755566899605 est de 0


Voici les premiers scénarii de type BDD !

En première analyse on peut à juste titre trouver ces deux scenarii
compliqués. L'équipe constate qu'il convient de développer un premier web
service de déclaration de commande et un second web service d'interrogation
des stock pour enfin développer le web service répondant au lancement de la
préparation. Bref notre première User Story ne semble donc être la vrai
première User Story. En effet comment peut-on lancer la préparation d'une
commande si nous n'avons pas la capacité d'intégrer ou créer des commandes.

Faire simple est une mantra que l'on ne se repera jamais assez. Dans ce cas
nous préconisons de "casser" la présente user story en 3 user stories.

La première user story serai :

Afin de pouvoir préparer des commandes.
Je peux enregistrer une commande.
En tant que Damien.

La second user story serait :

Afin de pouvoir gérer mon stock .
Je peux consulter le niveau de stock d'un produit.
En tant que Damien.


La première User Story à implémenter est donc celle portant sur
l'enregistrement des comandes.


