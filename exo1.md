1. Donnez la définition d’un système d’exploitation et citez trois des ressources qu’il gère.
==> Un system d'exploitation fait l'interface entre le le logiciel et le materiel (entre l'utilisateur et la machine), il gere la RAM, le processeur et les disques/peripheriques.
2. Expliquez le rôle respectif du noyau, du shell et des applications. Par quel composant les
applications doivent-elles obligatoirement passer pour accéder au matériel ?
==> Roles:
Le noyau : c'est le coeur du system d'exploitation, gere le materiel et les ressources.
Le shell: c'est un interpreteur de commande, fait l'interface entre l'utilisateur et le noyau.
Les applications: logiciels utilises par l'utilisateur.
Les applications doivent obligatoirement passer par le noyau pour avoir acces au materiel.
3. Que signifient les qualificatifs multitâche et multiutilisateur appliqués à Linux ?
==> Multitaches: plusieurs programmes peuvent s'executer en meme temps,
Multiutilisateur: plusieurs utilisateur peuvent travailler simultanement  sur la meme machine.
4. Pourquoi la date de référence des systèmes UNIX/Linux est-elle le 1er janvier 1970 ?
==> C'est l'« Epoch » : l'origine choisie par les créateurs d'UNIX. Le temps système compte les secondes écoulées depuis le 01/01/1970 à 00:00:00 UTC.
5. Qu’est-ce qu’une distribution GNU/Linux ? Citez deux distributions communautaires et deux
distributions commerciales.
==> Une distribution = noyau Linux + outils GNU + logiciels, empaquetés ensemble.
Communautaires : Debian, Fedora (ou Arch, Ubuntu).
Commerciales : Red Hat Enterprise Linux, SUSE Linux Enterprise. 
6. « Libre ne veut pas dire gratuit. » Expliquez cette phrase puis énumérez les quatre libertés
garanties par la licence GPL.
==> « Libre » concerne la liberté d'usage, pas le prix (on peut vendre du logiciel libre). Les 4 libertés :
exécuter le programme pour tout usage ;
étudier son fonctionnement et le modifier (accès au code source) ;
redistribuer des copies ;
distribuer ses versions modifiées.
7.  Dans la commande 
ls -lia /etc /home, identifiez le nom de la commande, les options et les arguments. Réécrivez-la sans regrouper les options.
commande: ls
option: -l -a -i
argument: /etc et /home
8. Quelle est la différence entre -l et --list ? À quoi sert le double tiret -- seul ?
==> -l est la forme courte (une lettre), --list la forme longue (un mot).
Le -- seul marque la fin des options : ce qui suit est traité comme argument (ex. rm -- -fichier).
9. Que signifient les invites $ et # ?
==> $ : invite d'un utilisateur normal. # : invite de l'administrateur (root).
10.  Donnez la commande qui permet de :
a. consulter la page de manuel décrivant le format du fichier 
/etc/passwd ==> man 5 psswd
b. rechercher par mot-clé dans les pages de manuel la commande 
clear ==> man -k clear
c. arrêter électriquement le serveur dans 15 minutes avec le message « Maintenance » ==> shutdown -h +15 "Maintenance" 
d. redémarrer immédiatement le serveur ==> shutdown -r now 
e. rappeler la dernière commande saisie ==> !!
f. rappeler la dernière commande commençant par ls ==> !ls
g. effacer l’historique de la session en cours (question théorique : ne l’exécutez pas pendant le TP). ==> history -c

