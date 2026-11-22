1. Donnez le chemin absolu du fichier linux.txt.
==> home/groupeA/alice/cours/linux.txt
2. Le répertoire courant est /home/groupeA/bob. Donnez le chemin relatif vers linux.txt.
==> cd ../alice/cours/linux.txt
3. Le répertoire courant est /home/groupeB/carla/projets/tp1. Donnez le chemin relatif vers le répertoire notes de bob.
==> cd ../../../../groupeA/bob/notes
4.  Indiquez ce qu’affiche chaque pwd de la séquence suivante (l’utilisateur est alice, son répertoire de connexion est 
/home/groupeA/alice) :
a. home/groupeA/bob 
b. home/groupeB/carla
c. home/groupeA/alice
d. home/groupeA/alice
5. Classez en chemins absolus ou relatifs : /etc/passwd,../alice, ./script.sh,cours/linux.txt, /, ...
==> Absolus: /etc/passwd , /
Relatifs: ../alice , ./script.sh, cours/linux.txt, ..
6. Pourquoi faut-il taper ./script.sh et non script.sh pour lancer un exécutable situé dans le répertoire courant ?
==> Le shell cherche les commandes uniquement dans les répertoires de la variable PATH, et le répertoire courant n'en fait pas partie. ./script.sh donne un chemin explicite,
alors le shell n'a plus besoin de chercher.

