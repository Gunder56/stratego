# Cahier Des Charges 

## Sommaire 

### 1_Introduction 

#### 1.1_Presentation du jeu stratego 
#### 1.2_Portee du jeu
#### 1.3_Terminologies

### 2_ Objectif du produit

### 3_Exigences du jeu

#### 3.1_Exigences fonctionnelles
#### 3.2_Exigences non fonctionnelles
#### 3.3_Exigences concernant le developpement du produit



# 1. Introduction

## 1.1 Présentation du jeu Stratego

Stratego est un jeu de société de stratégie et de bluff opposant deux joueurs, chacun dirigeant une armée composée de différentes unités militaires. Le jeu se déroule sur un plateau de 10 × 10 cases, dont certaines sont occupées par des lacs infranchissables. Chaque joueur dispose de 40 pièces représentant des unités de différents grades, possédant chacune une valeur et, pour certaines, des capacités particulières.

Au début de la partie, les joueurs procèdent au placement stratégique de leurs pièces sur les quatre premières rangées de leur côté du plateau. Ce placement est effectué de manière secrète afin de préserver l'identité et la valeur des unités vis-à-vis de l'adversaire. La partie se déroule ensuite au tour par tour, chaque joueur déplaçant une pièce ou attaquant une pièce ennemie.

Lorsqu'une attaque a lieu, les valeurs des deux pièces sont révélées et comparées. La pièce la plus puissante remporte le combat, tandis que la pièce perdante est éliminée. En cas d'égalité, les deux pièces sont éliminées. Certaines unités disposent de règles particulières, notamment l'espion, capable de vaincre le maréchal lorsqu'il l'attaque, le démineur, qui peut neutraliser les bombes, et l'éclaireur, qui peut se déplacer sur plusieurs cases en ligne droite.

L'objectif principal du jeu est de capturer le drapeau adverse tout en protégeant le sien. Stratego repose ainsi sur la réflexion, l'anticipation, la prise de décision et le bluff, puisque les joueurs doivent élaborer leurs stratégies à partir d'informations limitées concernant l'armée adverse.

## 1.2 Portée du jeu

Dans le cadre de ce projet, l'objectif est de développer une application informatique permettant de jouer à Stratego tout en facilitant l'apprentissage et la mémorisation des informations relatives aux pièces adverses. Le logiciel vise à reproduire les principales mécaniques du jeu original, tout en proposant une fonctionnalité supplémentaire destinée aux joueurs débutants.

L'application devra proposer deux modes de jeu :

- **Mode classique :** permet au joueur de jouer une partie de Stratego contre une intelligence artificielle simple, en respectant les règles du jeu.
- **Mode débutant :** reprend le fonctionnement du mode classique et fournit des informations supplémentaires sur les pièces adverses déjà découvertes. La valeur des pièces révélées lors des combats sera conservée et affichée. Les déplacements de certaines pièces adverses pourront également permettre de déduire leur nature, notamment lorsqu'un éclaireur effectue un déplacement de plusieurs cases. Une indication visuelle permettra de distinguer les pièces ayant déjà été déplacées, afin d'exclure la possibilité qu'il s'agisse d'une bombe ou du drapeau.

Le logiciel devra également assurer la gestion d'une nouvelle partie, le placement initial des pièces, le déroulement des tours, la validation des déplacements autorisés, la résolution des combats et la détermination de la victoire. Il devra garantir le respect des règles du jeu et empêcher l'exécution d'actions illégales.

Le projet se concentre sur la mise en œuvre des fonctionnalités essentielles de Stratego, avec une architecture suffisamment évolutive pour permettre l'ajout ultérieur de fonctionnalités telles que le mode deux joueurs, la sauvegarde et la reprise d'une partie, ou encore une intelligence artificielle plus avancée.

## 1.3 Terminologies

Afin de faciliter la compréhension du fonctionnement du jeu et de l'application, les termes suivants seront utilisés dans la suite du cahier des charges :

- **Plateau de jeu :** grille de 10 × 10 cases sur laquelle se déroule la partie, comprenant des cases accessibles et des zones de lacs infranchissables.
- **Joueur :** participant à la partie, contrôlant une armée et prenant des décisions de déplacement et d'attaque.
- **Pièce / Unité :** élément représentant un membre de l'armée, caractérisé par un grade, une valeur, une position et éventuellement une capacité spéciale.
- **Grade :** rang militaire associé à une pièce, déterminant généralement sa puissance lors d'un combat.
- **Valeur :** nombre associé au grade d'une pièce, permettant de comparer la puissance de deux unités lors d'une attaque.
- **Maréchal :** pièce de valeur 10, correspondant à l'unité la plus puissante de l'armée.
- **Espion :** pièce de valeur 1, possédant la capacité particulière de vaincre le maréchal lorsqu'il l'attaque.
- **Démineur :** pièce de valeur 3, capable de neutraliser une bombe en l'attaquant.
- **Éclaireur :** pièce de valeur 2, capable de se déplacer sur plusieurs cases en ligne droite, sous certaines conditions.
- **Bombe :** pièce immobile éliminant toute unité qui l'attaque, à l'exception du démineur.
- **Drapeau :** pièce immobile dont la capture entraîne la victoire du joueur adverse.
- **Placement initial :** phase précédant le début de la partie durant laquelle chaque joueur dispose ses pièces sur sa zone de départ.
- **Déplacement :** action consistant à déplacer une pièce vers une case autorisée du plateau, en respectant les règles de mouvement.
- **Attaque :** action consistant à déplacer une pièce sur une case occupée par une unité adverse afin de déclencher un combat.
- **Combat / Rencontre :** confrontation entre deux pièces adverses entraînant la comparaison de leurs valeurs et l'application des règles particulières.
- **Élimination :** retrait d'une pièce du plateau à la suite d'un combat perdu ou d'une règle spéciale.
- **Bluff :** mécanisme stratégique reposant sur la dissimulation de la valeur des pièces afin d'inciter l'adversaire à prendre des décisions sans disposer de toutes les informations.
- **Mode classique :** mode de jeu dans lequel les informations concernant les pièces adverses restent limitées aux révélations prévues par les règles.
- **Mode débutant :** mode de jeu proposant une visualisation et une mémorisation des informations connues ou déduites concernant les pièces adverses.


# 2. Les objectifs du produit

## 2.1 Définition du produit

Le produit consiste à développer une version informatique du jeu de stratégie *Stratego*. Il s'agit d'un jeu de plateau opposant deux joueurs, dont l'objectif principal est de capturer le drapeau adverse tout en protégeant le sien. Le jeu repose sur des mécanismes de déplacement, d'affrontement entre unités et de stratégie, où chaque joueur doit prendre des décisions en fonction des informations dont il dispose.

L'application devra permettre à un utilisateur de jouer contre une intelligence artificielle (IA), en proposant une expérience de jeu accessible et intuitive. Elle devra reproduire les principales règles du jeu original, notamment la gestion des pièces, les déplacements autorisés, les combats et les conditions de victoire.

Le produit devra également proposer différents modes de jeu afin de s'adapter au niveau des joueurs. Le mode classique reposera sur le principe de l'information cachée, tandis que le mode débutant permettra de faciliter la compréhension des mécanismes du jeu grâce à des informations supplémentaires sur les pièces adverses.

L'objectif est de proposer une application fonctionnelle, simple à prendre en main et respectant les règles fondamentales de Stratego, tout en permettant une évolution future vers de nouvelles fonctionnalités.

## 2.2 Contexte économique du produit

Le projet s'inscrit dans un cadre universitaire et pédagogique, dans le contexte de la formation en Licence 3 Informatique, parcours Génie logiciel. Le développement du jeu Stratego constitue avant tout un exercice de mise en pratique des compétences acquises au cours de la formation, notamment en programmation, conception logicielle, structuration d'un projet et développement d'une application interactive.

Le produit n'a pas pour objectif initial d'être commercialisé. Il est développé dans le cadre d'un projet universitaire et ne nécessite donc pas de modèle économique particulier. Les ressources mobilisées sont principalement le temps de travail des membres du projet ainsi que les outils de développement mis à leur disposition.

Toutefois, le jeu pourra éventuellement être enrichi dans le futur afin d'offrir une expérience plus complète aux utilisateurs. Ces évolutions pourraient permettre d'améliorer son attractivité et d'envisager une utilisation au-delà du cadre pédagogique.

## 2.3 Contexte d'exploitation du produit

Le jeu Stratego sera conçu pour être utilisé sur un ordinateur, dans un environnement permettant l'exécution de l'application. L'utilisateur devra pouvoir lancer une partie, configurer son placement initial, effectuer ses déplacements et interagir avec l'intelligence artificielle au cours de la partie.

L'application devra proposer une interface claire permettant de visualiser le plateau, les pièces disponibles, les déplacements possibles et les résultats des affrontements. Les différentes actions réalisées par le joueur devront être compréhensibles et les règles devront être appliquées automatiquement par le programme.

Le produit devra fonctionner de manière autonome, sans nécessiter de connexion à Internet pour jouer. L'intelligence artificielle sera intégrée directement à l'application et permettra à un joueur humain de s'opposer à un adversaire contrôlé par l'ordinateur.

L'exploitation du produit devra ainsi être simple et accessible, afin de permettre à un utilisateur de démarrer et de jouer une partie sans connaissances techniques particulières.
