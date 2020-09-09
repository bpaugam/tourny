# tourny

## Description
Tourny est une application permettant à un organisateur d'organiser des tournois de sports ou de jeux (contrée, jeux-vidéo, etc...).

Un tournoi consiste à lister des **équipes créées pour l'occasion constituées de un ou plusieurs joueurs** puis, une fois **lancé**, à dresser le **tableau des matches** prévus ("bracket") dans un temps déterminé (date de début et de fin).

![8 team single elimination example](/8-Team-Single-Elimination.gif?raw=true "8 team single elimination example")

Un tableau distingue plusieurs rangs ou "rounds" (par exemple : "16<sup>ièmes</sup>", "8<sup>ièmes</sup>", "quarts", "semi-finale", "finale").

À chaque intersection du tableau correspond un match, qui va opposer les deux équipes vainqueurs du rang précédent, à part pour le premier rang, où on retrouvera toutes les équipes dans un ordre aléatoire déterminé au lancement du tournoi. Chaque match peut être daté, parfois à l'avance.

Chaque match donne lieu à une ou plusieurs parties (des sets au tennis par exemple) entre les équipes opposantes. Le nombre de parties est déterminé au niveau du tournoi. Dans ce MVP on ne gèrera que des tournois en 1, 3 ou 5 manches : "sudden death", "best of three" ou "best of five".

À chaque partie, le score est renseigné par l'organisateur du tournoi dans l'application. Une fois le match terminé, l'équipe vainqueuse est désignée et "monte" au rang suivant.

Une fois la finale remportée, l'équipe vainqueuse est désignée championne du tournoi, et le tournoi est supposé terminé.

Un tournoi lancé doit pouvoir repasser à sa phase de préparation si jamais aucun match n'a encore eu lieu, débloquant ainsi la modification des équipes et de leurs joueurs.

Un tournoi lancé pourra être abandonné en cours de route. Dans ce cas, aucun vainqueur n'est désigné.

Un tournoi, une fois terminé ou abandonné, ne peut plus être modifié.

![Les statuts d'un tournoi](/tournament-statuses.jpg?raw=true "Les statuts d'un tournoi")

## Les fonctionnalités

- Créer le tournoi, puis renseigner les équipes participantes et enfin le lancer.
- Visionner le tableau, automatiquement créé lors du lancement du tournoi.
- Consulter un match et en saisir les parties et leur score.
- Consulter des matches disputés par une équipe d'un tournoi.
- Abandonner un tournoi.

Bonus :
- Modéliser la possibilité pour une équipe de déclarer forfait.
- Consulter les matches de la semaine ou d'un jour pour un tournoi / sur tous les tournois.
- Consulter les matches disputés par un joueur sur tous les tournois auxquels il a participé ou va participer.
- Modéliser les ligues, qui organisent des tournois récurrents  (exemple : UEFA Champions League).
- Modéliser l'organisation à laquelle une équipe d'un tournoi peut appartenir (exemple : le PSG), et permettre de consulter tous les matches des équipes qu'elles a placé dans tous les tournois.
- Permettre aux opposants d'un match d'en saisir et approuver ou non les scores et le résultat final. En cas de désaccord, l'organisateur du tournoi tranche.

## Nota bene

L'enjeu de cet exercice n'est pas de définir l'algorithme permettant de dresser le tableau du tournoi à partir des équipes. On considérera qu'un développeur brillant s'en sera occupé.

## Les questions à se poser
- Comment modéliser la relation entre les différentes ressources ? Le concept de sous-ressource s'applique-t-il ?
- Comment modéliser le fait qu'un match oppose toujours 2 équipes ? Faut-il le modéliser en 1-N ou en 1-2 ?
- Comment modéliser le tableau ? Faut-il créer les matches à l'avance ? Comment assigner les opposants de chaque match ? Comment appliquer le principe d'immutabilité maximale ?
- Comment modéliser le changement de statut du tournoi ?