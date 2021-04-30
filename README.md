# Groupe: PATEL Monali, SALLOUM Jad

Projet: Jeu RPG avec règles uniques.

Le RPG que nous avons défini consiste en un jeu durans lequel le joueur doit se battre contre des ennemis aux stats variantes, afin d'abattre le démon.
Pour cela, nous avons aboli le système de niveaux commun à la majorité des RPG, pour se focaliser sur un système de stats:

Les stats du joueur sont séparées comme montré ci-dessous:

Attaque
Défense
HP

Au lieu de faire monter ces stats durant une montée de niveau, celles-ci montent lors de l'utilisation de compétences.
Chaque classe de personnage possède 4 compétences: 

une attaque de base, infligeant des dégats variés et augmentant de façon permanante l'attaque
une compétence unique à la classe, et pouvant augmenter plus ou moins l'attaque de façon permanante
une compétence défensive, augmentant la défense pendant 1 tour et montant la défense de façon permanante
une compétence de soin, récupérant un pourcentage de vie du joueur, et augmentant les HP de façon permanante.

Il existe 3 classes: 
le Guerrier, classe puissante tant en attaque que en défense mais manque d'un moyen facile de se soigner. Utilise frequemment des objets

le Mage, classe variée qui possède moins de puissance d'attaque que le guerrier mais avec son buff le surpasse amplement. Possède une défense moindre mais un soin puissant.

Le Voleur, classe douée aux combats qui durent, grace à une attaque similaire au guerrier ainsi qu'à un poison faisant effet sur l'adversaire à chaque tour, allié ou ennemi. Possède moins de défense que le guerrier et moins de soin que le mage.


Comme indiqué au dessus, le joueur possédera des objets lui permettant de se soigner au combat. Ces potions se trouveront dans les drop des ennemis ainsi que disponibles à la boutique.
Le joueur ne peut pas se soigner hors des combats avec ces potions, mais peut se soigner dans la boutique.

La boutique permet d'acheter des potions ainsi que de se soigner (prix augmentant en fonction de la vie à soigner).

Le joueur peut hors combat:
Lancer un combat contre un adversaire de son choix
Analyser ses stats afin de se préparer
Accéder à la boutique
Quitter le jeu (demande à sauvegarder / quitter / revenir au menu)




Nous avons rencontré plusieurs difficultés dans la création de se projet, notemment au départ:

Nous avions pour stratégie de créer plusieurs classes dans des fichiers cpp, liés entre eux par des fichiers h afin d'utiliser des fonctions et les informations necessaires.
Cependant, nous avons abandonné cette méthode après avoir découvert que cette méthode ne fonctionne pas (les classes n'arrivaient pas à s'instancier et la page main de trouvait pas la fonction en question, bien qu'elle soit bien liée à la page via le header)

Nous sommes donc partis sur un code tenant sur une seule page.


Notre prochaine épine était de découvrir que la fonction cin (cout fonctionne bien) ne prend pas les informations après que le joueur appuie sur entrée,
et ce, peu importe la méthode de cin employée (getline, ou autre y compris).

Malheureusement, ce problème n'a pas pu être résolu, et nous avons donc un jeu non fonctionnel à cause de cela.


Le deuxième problème majeur empêchant ce fonctionnement vient de la structure à une page du code:
les classes créées permettent le bon fonctionnement des fonctions à l'interieur, cependant, si une fonction d'une classe essaie d'accéder à une fonction d'une classe initialisée après celle-ci, alors la classe n'est pas reconnu et la fonction non trouvée.

Ce problème est repérable dans la fonction game(Joueur j) dans la classe Joueur, car on ne peut pas accéder aux fonctions du lancement des combats.


Hormis ces difficultées, nous avons pu tester les différentes fonctions séparemment, et ainsi corriger les erreurs sans le fonctionnement général du jeu.
Nous avions structuré notre temps afin d'avoir des objectifs principaux et secondaires pour le code du jeu:

Nous avons mis en priorité le gameplay même du jeu, et omis les objets. Dans cette première version, la boutique ne servait qu'à soigner le joueur et
le joueur ne possédait pas d'objet en combat.

La 2eme version à rajouté les objets dans le jeu. cela à changé radicalement le code, mais d'une manière positive et naturelle, qui ne nous a pas
ralenti à cause de suppression de code déjà mis.

Après avoir réussi ces fonctionnalités, nous avons fait une vérifiaction des erreurs entière du code, ainsi que mis des commentaires sur les lignes nécessaires.

Cette vérification étant accomplie, nous avons essayé de créer un système de sauvegarde de partie, et charger une partie, comme prévu initiallement.



Lors de la recherche du système de sauvegarde, nous sommes tombés sur un problème d'enregistrement du fichier: en effet, quoi que l'on fasse,
le fichier enregistré ne sera pas du type voulu (.txt) mais un fichier "file", c'est à dire sans extention.
Ceci étant un problème unique à nous, nous n'avons pas trouvé de solution fonctionnelle.

Nous avons essayé d'utiliser la librairie <filesystem> afin d'y remédier cependant celle-ci à provoqué une dizaine d'erreurs rendant le programme
complêtement non fonctionnel (il c'est mis à lancer la fonction save() alors qu'elle n'a jamais été appelée).

La fonction de chargement de partie a aussi été implémentée, mais les tests sont non concluent dues aux problèmes de sauvegarde.




Le plan brouillon du projet est mis dans le fichier planDuProjet.txt si vous souhaitez jeter un coup d'oeil. Nous allons plus en détail dans la structure du gameplay et dans les détails des informations.



