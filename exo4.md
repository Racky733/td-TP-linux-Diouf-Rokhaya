Q1. Créer l'arborescence en une seule commande
mkdir -p tp_linux/docs/cours tp_linux/docs/td tp_linux/sauvegardes

Q2. Fichiers vides dans cours, chap1.txt daté du 01/01/2025 à 12h00
cd tp_linux/docs/cours
touch chap1.txt chap2.txt chap6.txt
touch -t 202501011200 chap1.txt
ls -l

Q3. Contenu de tp_linux en récursif, puis avec les fichiers cachés
ls -R tp_linux
ls -Ra tp_linux
Un répertoire vide contient au minimum 2 références : "." (lui-même) et ".." (son parent).

Q4. Informations sur le répertoire lui-même
ls -ld tp_linux
"ls -l tp_linux" ne convient pas car il affiche le CONTENU du répertoire, pas le répertoire lui-même. L'option -d est nécessaire.

Q5. Numéros d'inode, puis tri par date (plus ancien en premier)
ls -i tp_linux/docs/cours
ls -ltr tp_linux/docs/cours
(-t trie du plus récent au plus ancien, -r inverse l'ordre.)

Q6. Prédiction puis vérification (dans tp_linux/docs/td)
cd ~/tp_linux/docs/td
touch fic1 fic2 fic3
mkdir rep

a. mv fic1 fic1_bis
   Renomme fic1 en fic1_bis.
b. cp fic2 rep
   Copie fic2 dans rep (rep/fic2), l'original reste.
c. cp fic2 rep/fic2_copie
   Copie fic2 dans rep sous le nom fic2_copie.
d. mv fic3 repinexistant
   repinexistant n'existe pas : fic3 est simplement renommé en "repinexistant" (un fichier, pas un répertoire).
e. mv fic1_bis fic2 rep
   Déplace fic1_bis et fic2 dans rep. Comme rep/fic2 existe déjà, il est écrasé sans avertissement (sans l'option -i).

Q7. Copier docs dans sauvegardes en conservant dates et permissions
cd ~
cp -a tp_linux/docs tp_linux/sauvegardes
Options nécessaires : -r (récursif) et -p (préserve dates et permissions). -a les regroupe (et plus encore).

Q8. Supprimer sauvegardes/docs
rmdir tp_linux/sauvegardes/docs
Message : "Le répertoire n'est pas vide". rmdir ne supprime que les répertoires vides.
Suppression correcte :
rm -r tp_linux/sauvegardes/docs

Q9. Fichier nommé -test
touch ./-test
rm -test
Erreur : rm interprète "-test" comme une série d'options (-t, -e, -s...) et non comme un nom de fichier ("option invalide").
Deux façons de le supprimer :
rm ./-test
rm -- -test
