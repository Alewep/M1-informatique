# Programmation Système 

## Processus

### Etats d'un processus 
un processus est un programme en cours d'exécution qui peut être dans 3 états :
 - Prêt : attente d'être choisi par l'ordonnanceur 
 - En cours d'exécution : peut revenir à l'état prêt quand l'ordonnanceur le décide
 - Bloqué : le processus est en attente de ressource.

Deux mode pour un processus en cour d'exécution  :
 - Utilisateur : exécution du code spécifique de l'application 
 - Noyau : exécution d'appel système
 
### Composition d'un processus
Le système d'exploitation associe à chaque processus :
- code du programme 
- Un espace d'adressage. Le processus ne pourra accéder qu'à cette mémoire là.
- le ** process control block ** contenant l'identifiant le pid, le ppid, l'uid, les descripteurs de fichier ouverts, etc.

*Il est possible de sortir de l'espace d'adressage par exemple nous déclarons un tableau de taille 10 et nous voulons accéder à l'indice 10000* 

### Création d'un processus 

Le système d'exploitation maintient une arborescence des processus ( commande unix `pstree`) racine est le processus init de pid 1.

Un nouveau processus est crée par **fork**.

**fork** duplique le processus courant en créant un processus fils identique au processus courant. l'espace d'adressage mémoire est dupliqué.

### Fin d'exécution d'un processus

Quand un processus se termine, Il retourne une valeur à son processus père.
Si égale à 0 exécution bien terminé sinon erreur.

### Remplacement de processus

les fonction execl, execlp, etc. permettent d'appeler un programme exécutable en remplaçant le processus courant par un processus correspondant à l'exécuta
