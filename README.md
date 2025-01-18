Jeu d'Échecs en Réseau

Ce projet est une implémentation d'un jeu d'échecs en réseau, où deux joueurs peuvent s'affronter à distance. Le jeu est composé d'un serveur (Server2.c) et d'un client (Client2.c). Le serveur gère la logique du jeu et la communication entre les deux clients, tandis que chaque client gère l'interface graphique et les interactions utilisateur.


Prérequis

Pour compiler et exécuter ce projet, vous aurez besoin des éléments suivants :

Compilateur C : GCC ou un autre compilateur C.
Bibliothèques SDL2 et SDL2_image : Pour l'interface graphique.
Bibliothèques réseau : Les bibliothèques standard pour la gestion des sockets (arpa/inet.h, sys/socket.h, etc.).


Installation des dépendances

Sur une distribution Linux basée sur Debian (comme Ubuntu), vous pouvez installer les dépendances nécessaires avec les commandes suivantes :

  sudo apt update
  sudo apt install build-essential libsdl2-dev libsdl2-image-dev


Compilation

Compilation du Serveur

Pour compiler le serveur, utilisez la commande suivante :

  gcc Server2.c -o Server2

Compilation du Client

Pour compiler le client, utilisez la commande suivante :

  gcc Client2.c -o Client2 -lSDL2 -lSDL2_image


Exécution

Lancement du Serveur

Lancez le serveur en exécutant la commande suivante :

  ./Server2

Le serveur écoutera sur le port 30000 et attendra que deux clients se connectent.

Lancement des Clients

Lancez le premier client en exécutant simplement :

  ./Client2

Le client se connectera automatiquement au serveur en utilisant l'adresse IP codée en dur dans le fichier Client2.c (dans ce cas, 172.26.136.239).

Lancez le deuxième client de la même manière :

  ./Client2

Le deuxième client se connectera au serveur et le jeu commencera.


Fonctionnement du Jeu

Le client 1 joue avec les pièces blanches et le client 2 joue avec les pièces noires. Les joueurs alternent les tours pour déplacer leurs pièces. Le serveur gère la synchronisation des mouvements entre les deux clients.


Règles du Jeu

Le jeu suit les règles classiques des échecs, y compris les mouvements spéciaux comme le roque et la prise en passant. Les joueurs peuvent promouvoir leurs pions lorsqu'ils atteignent la dernière rangée.


Gestion des Erreurs

Si un client se déconnecte, le serveur en informe l'autre client et met fin à la partie.

Si le serveur rencontre une erreur lors de la communication, il ferme les connexions et termine proprement.


Nettoyage

Après la fin de la partie, le serveur et les clients ferment leurs sockets et libèrent les ressources.


Améliorations Possibles

Interface graphique améliorée : Ajouter des animations, des effets sonores, etc.


Gestion des erreurs réseau : Améliorer la gestion des déconnexions inattendues.

Mode spectateur : Permettre à des observateurs de regarder la partie en cours.

Configuration de l'adresse IP du serveur : Permettre à l'utilisateur de spécifier l'adresse IP du serveur via des arguments en ligne de commande ou un fichier de configuration.


Auteurs

Ce projet a été développé par Adrien PANGUEL et Mohamed SAAD dans le cadre d'un projet personnel ou académique.

Licence

Ce projet est sous licence MIT. Vous êtes libre de l'utiliser, de le modifier et de le distribuer selon les termes de la licence.

Profitez de votre partie d'échecs en réseau ! 🎉
