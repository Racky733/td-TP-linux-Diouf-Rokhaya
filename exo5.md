Préparation
cp /etc/passwd ~/tp_linux/passwd.txt
cd ~/tp_linux

Q1. file sur passwd.txt, /etc, /bin/ls et /dev/null
file passwd.txt /etc /bin/ls /dev/null
Remarque : file détecte le type d'après le CONTENU, pas l'extension :
passwd.txt = texte ASCII, /etc = directory, /bin/ls = exécutable ELF, /dev/null = fichier spécial caractère.

Q2. 5 premières lignes, 3 dernières, numérotées, à l'envers
head -n 5 passwd.txt
tail -n 3 passwd.txt
cat -n passwd.txt
tac passwd.txt

Q3. Nombre de comptes et nombre d'octets
wc -l passwd.txt
wc -c passwd.txt

Q4. Tri selon l'UID (3e champ, séparateur :)
sort -t: -k3 -n passwd.txt
sort -t: -k3 -nr passwd.txt
sort -t: -k3 -n -o passwd_trie.txt passwd.txt

Q5. nombres.txt
echo -e "110\n20\n3" > nombres.txt
sort nombres.txt      -> 110, 20, 3
sort -n nombres.txt   -> 3, 20, 110
Explication : sans -n, le tri est alphabétique (caractère par caractère, "110" < "20" < "3"). Avec -n, le tri est numérique.

Q6. taille.txt, du plus gros au plus petit
echo -e "3G\n120M\n45K\n2G\n980M\n7M\n15G\n512K" > taille.txt
sort -hr taille.txt
Option qui comprend K, M et G : -h (human-numeric) ; -r inverse l'ordre.

Q7. Suivi en temps réel
Terminal 1 : tail -f taille.txt
Terminal 2 : echo "1G" >> taille.txt
Observation : la ligne "1G" apparaît aussitôt dans le premier terminal. Arrêt avec Ctrl+C.

Q8. Création des fichiers
mkdir recherche
cd recherche
touch rapport1 rapport2 rapport12 rapports rapport_final.txt bilan.txt bilan.log
cd ..

a. find recherche -name "rapport*"
   Prédiction : rapport1, rapport2, rapport12, rapports, rapport_final.txt (tout ce qui commence par "rapport").
b. find recherche -name "rapport?"
   Prédiction : rapport1, rapport2, rapports (exactement un caractère après "rapport").
c. find recherche -name "rapport[12]*"
   Prédiction : rapport1, rapport2, rapport12 (le caractère après "rapport" est 1 ou 2).
d. find recherche -name "*.txt"
   Prédiction : rapport_final.txt, bilan.txt.

Q9. Tous les répertoires sous ~/tp_linux
find ~/tp_linux -type d

Q10. Supprimer les fichiers .log de recherche
find recherche -name "*.log" -exec rm {} \;
{} : remplacé par chaque fichier trouvé.
\; : marque la fin de la commande -exec (le \ empêche le shell d'interpréter le ;).

Q11. grep sur passwd.txt
a. grep "^root:" passwd.txt
b. grep "/bin/bash$" passwd.txt
c. grep -v "nologin$" passwd.txt
d. grep -i "ROOT" passwd.txt

Q12. Recherche récursive de HISTSIZE dans /etc
grep -r "HISTSIZE" /etc
Certains fichiers ou dossiers de /etc ne sont lisibles que par root : un utilisateur ordinaire n'a pas la permission de lecture, d'où "Permission denied". (On peut les masquer avec 2>/dev/null.)

Q13. whereis
whereis -b ls       (binaire uniquement)
whereis -m passwd   (pages de manuel uniquement)
