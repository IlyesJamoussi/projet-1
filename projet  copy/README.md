###################################################################  PATHFINDER ##############################################################################

Ce projet vise à programmer un robot capable d'identifier des extrémités, traverser des parcours, et générer un rapport complet sur ses actions.


##### Contenu du Projet
app/ : Contient le fichier source principal  à exécuter pour contrôler le robot.
lib/ : Regroupe les bibliothèques nécessaires pour gérer les capteurs, les moteurs, les led, les interrupteurs et les modes du robot.


###### Configuration Matérielle
Le robot est équipé des capteurs suivants :
Suiveur de ligne Maker Line : Permet de détecter et suivre une ligne.
Capteur de distance Sharp GP2Y0A21YK0F : Utilisé pour détecter des objets à distance.     
Piézoélectrique : Permet d’émettre des signaux sonores, utilisé comme indicateur sonore ou pour signaler un événement spécifique.


##### Comment Démarrer

Branchement : Vérifiez les connexions suivantes :
Le suiveur de ligne est connecté aux ports analogiques : A1 à A5.
Le capteur de distance est branché sur le port analogique A0.
Les moteurs sont connectés aux ports PWM pour le contrôle :
Moteur droit : D4 et D6.
Moteur gauche : D5et D7.
Compilation : Pour compiler le projet, utilisez make depuis le dossier app.
Chargement : Téléchargez le programme sur le microcontrôleur avec make install.
Note : Ne connectez pas de périphériques sur les ports B lors de la compilation.

##### Modes d'Opération
Le robot propose trois modes principaux :

-chercher extrémité : Le robot doit Rejoindre une des extrémités du parcours (C, D ou E) en se déplaçant uniquement sur les segments de ruban sans sauter d’une intersection à une autre. 
Allume sa DEL pour identifier l’extrémité, C : vert, D : rouge, E : ambre
-traverser parcours : Le robot détecte un poteau  situés à 10 cm tout en empruntant le chemin le plus court pour l'atteindre. Une fois le poteaux détecté, 
il se déplace vers son point de repère final (point E).
-Afficher rapport : Le robot génère un rapport détaillé via RS-232, incluant les points de départ, les obstacles rencontrés, et les positions atteintes.

######  Guide de Démarrage
    # Mode 1 : Recherche d’extrémité
Placez le robot sur la table en respectant ces contraintes :
1- Le centre de rotation doit être sur le point A ou B.
2- Le nez du robot doit être centré sur un des quatre segments de ruban touchant le point.
3- Une fois le clignotement de confirmation de mode terminé, le robot attend 2 secondes avant de se mettre en marche.

    #Mode 2 : Traversée de parcours
Placez le robot sur la table en respectant ces contraintes :
1- Le centre de rotation doit être sur le point C ou D.
2- Le nez du robot doit être centré sur le segment reliant le point à l’intersection en « X ».
3- Placez un poteau sur le point 1 ou 2, bien centré sur l’intersection.
4- Appuyez sur le bouton Interrupt pour démarrer.
5- Une fois le signal reçu, le robot attend 2 secondes, puis se met en marche pour :
6- À chaque étape, repositionnez le poteau et relancez le robot en appuyant sur Interrupt.
7- Après la dernière immobilisation, retirez le poteau du parcours et appuyez une dernière fois sur Interrupt.

    #Mode 3:
1- Connectez le robot à un PC à l’aide d’un câble USB.
2- Lancez l’application serieViaUSB avec l’option -l.


Auteurs
Wael El karoui
Ilyes Jamoussi
Mariama Seydi 
Nirmine Benarrait