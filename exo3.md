1. Affichez votre login, votre UID, votre groupe principal et la liste de vos groupes (whoami,id,id -u, id -gn, id -Gn).
whoami      # login
id          # UID, GID, groupes
id -u       # UID seul
id -gn      # nom du groupe principal
id -Gn      # noms de tous les groupes

2.  Affichez les utilisateurs connectés avec who. Ouvrez une seconde console (Ctrl+Alt+F2 ou un second terminal) et relancez who : que constatez-vous ? Que signifient tty et pts ?
==> Avec la seconde console, who affiche une ligne de plus (une nouvelle session). tty = terminal texte (console virtuelle, ex. Ctrl+Alt+F2). 
pts/ = pseudo-terminal (terminal graphique ou connexion SSH).

3.  Avec la commande 
date, affichez :
a. la date du jour au format AAAA-MM-JJ ==> date +%Y-%m-%d
b. l’heure au format hh:mm:ss ==> date +%H:%M:%S
c. le quantième (numéro du jour dans l’année) du 29 juillet 2015 ==> date -d 2015-07-29 +%j
d. le nom du jour de la semaine de votre date de naissance ==> date -d 2006-09-06 +%A
e. le nombre de secondes écoulées depuis le 1er janvier 1970 ==> date +%s
f. le numéro de la semaine en cours ==> date +%V

4.  Avec echo, affichez sur deux lignes, séparées par une tabulation après les deux-points : : suivi de votre nom, puis Nom Classe : suivi de votre classe.
Quelle option est indispensable et pourquoi ?
==> echo -e "Nom:/tRokhayaDiouf/nClasse:/tDBE"
L'option -e est indispensable : sans elle, \n et \t sont affichés tels quels au lieu d'être interprétés (retour à la ligne et tabulation).

5.  Affichez votre historique avec history (n’exécutez surtout pas history -c : vous effaceriez la preuve de vos tests). Rappelez une commande par son numéro
(dernière commande commençant par date (!n), puis la !date). Écrivez l’historique dans le fichier avec history -w et vérifiez avec tail ~/.bash_history.
==>
history
!12          # rappelle la commande n°12 (adapte le numéro)
!date        # dernière commande commençant par "date"
history -w
tail ~/.bash_history

6. Tapez who puis appuyez deux fois sur Tab : que se passe-t-il ? Même question avec wh.
==> Deux Tab affichent la liste des complétions possibles. who + Tab Tab → who, whoami, … wh + Tab Tab → whatis, whereis, which, who, whoami, etc.

7. Ouvrez man ls et, avec la recherche /, trouvez l’option qui trie les fichiers par taille. Quittez avec q.
==> man ls, puis /size et Entrée (n pour l'occurrence suivante) : l'option est -S (tri par taille, du plus grand au plus petit). Quitter avec q.
