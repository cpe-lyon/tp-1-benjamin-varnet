# Compte rendu de TP1

**Toutes les commandes ont été entrées en root !**

## Exercice 2. Prise en main de l’interpréteur de commandes
### Manuel
**Question 1 :**<br/>
Rôle de la commande which : La commande which prend un ou plusieurs paramètres. Pour chaque fichiers passés en paramètre, cette commande imprime le chemin de ou des éxécutables dans le terminal.
**Question 2 :**<br/>
Pour rechercher le terme "option" par exemple dans le man de which il faut taper les commandes suivantes : man which puis quand la page de man est ouverte, il faut faire : /option pour aller au premier terme option sur la page puis faire n pour passer au suivant<br/>
**Question 3 :**<br/>
Pour quitter le manuel il suffit de faire q<br/>
**Question 4 :**<br/>
Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ? Lorsque nous faisons un man ls par exemple, il y a marqué en haut à gauche : LS(1), ce qui veut dire que nous sommes dans la section 1 du man de la commande ls. Pour aller sur une section particulière d'une commande, il faut faire un man 2 open pour aller dans la deuxième section de la commande open.<br/>
### Navigation dans l’arborescence des fichiers
**Question 1 :**<br/>
Pour aller dans /var/log, il faut faire un cd /var/log<br/>
**Question 2 :**<br/>
Pour remonter dans l'arbroescence, il faut donc faire un cd ..<br/>

Pour revenir au dossier précédent sans utiliser le chemin en /..., il faut faire un cd -<br/>
**Question 5 :**<br/>
Nous ne pouvons pas accéder au dossier root car il nous faut des droits supplémentaires. --> la commande cd /root ne fonctionne donc pas.<br/>
**Question 6 :**<br/>
Le systeme nous demande le mot de passe de notre comopte car nous executons une commande avec sudo, ce qui execute une commande avec les droits root<br/>
**Question 7 :**<br/>
Pour créer un dossier il faut faire mkdir "nom du dossier". Notre dossier sera donc créé. Puis, il faut faire un cd /Notrenouveaudossier ce qui va nous placer dans notre dossier créé précéemment, puis, il faut faire un mkdir dans ce dossier pour créé une sorte de sous-dossier.<br/>

Pour créé un fichier, il suffit de faire la commande suivante : touch "nom du fichier"<br/>

Pour supprimer un fichier : il faut faire un rm "nom du fichier" Pour supprimer un dossier : il faut faire un rm "nom du dossier" -r (le -r permet de forcer la suppression du dossier même s'il n'est pas vide)<br/>
### Commandes importantes
**Question 1 :**<br/>
Pour afficher l'heure, il faut faire la commande suivante : date<br/>

La commande time est un chronomètre pour le temps d'éxécution de la commande Exemple : time man, time ls, time xxx.sh --> retourne le temps d'éxécution qui a été écoulé.<br/>
**Question 2 :**<br/>
ls --> Liste les dossiers et les fichiers présents dans le répertoire où l'on est la --> Donne tous les fichiers et dossiers même les fichiers cachés (fichiers qui commencent par un .)<br/>
**Question 3 :**<br/>
Pour trouver le programme ls, il faut faire un find / -name ls Cette commande nous retourne où est le programme ls, il nous retourne par exemple : /usr/bin/ls<br/>
**Question 4 :**<br/>
Il n'y a pas d'entrée de manuel pour la commande ll, car il s'agit d'un alias, la commande ll résulte de l'alias suivant : alias ll alias ll='ls -alF<br/>

**Question 5 :** Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ? <br/>
La commande : ls /bin<br/>

**Question 6 :** Que fait la commande ls .. ? <br/>
Donne ce qui est présent dans le répertoire parent de là où nous sommes actuellement<br/>

**Question 7 :** Quelle commande donne le chemin complet du dossier courant ?<br/>
 La commande : pwd<br/>

**Question 8 :** Que fait la commande echo 'yo' > plop exécutée 2 fois ? <br/>
Ecris yo dans le fichier plop<br/>

**Question 9 :** Que fait la commande echo 'yo' >> plop exécutée 2 fois ?  <br/>
Affiche yo et fait un retour à la ligne à chaque éxécution de commande alors que la commande précdenté réécris au début du fichier<br/>

**Question 10 :** A quoi sert la commande file ? <br/>
Essayez la sur des fichiers de types différents. Commande donne la description du fichier que l'on spécifie<br/>

**Question 11 :** Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi : qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?<br/>

Prend en compte les modifications. Si on supprime toto, titi devient indépendant ça casse le lien<br/>

**Question 12 :** Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle conséquence cela a-t-il sur tutu ?<br/>

si on modifie titi tutu est également modifié. Alors que l'inverse n'est pas vrai. Si on supprime le fichier titi, tutu sera encore visible par la commande ls. Cependant, si on supprime titi, tutu ne pourra pas être lu par le système.<br/>

**Question 13 :** Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ? le raccourci Ctrl + C<br/>

Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20. <br/>
Exemple : <br/>
head /var/log/syslog -n 5 <br/>
tail /var/log/syslog -n 5 <br/>
head -n 20 /var/log/syslog  | tail -n 10<br/>

**Question 14 :** Que fait la commande dmesg | less ? Affiche tous les messages qui sont dans le buffer du kernel. La commande less s'apparente à la commande more mais avec des fonctionnalités en plus comme la possibilité de revenir en arrière quand on a avancé dans le fichier.<br/>

**Question 15 :** Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page de manuel de ce fichier ? /etc/passwd donne tous les comptes qui sont dans l'OS avec leur répertoire /home personnel.<br/>julien:x:1000:1000:julien:/home/julien:/bin/bash nom d'utilisateur:x car c'était anciennement le mot de passe:id du user:id du groupe de user:groupe:répertoire de travail du user par défaut:intérpréteur de commande utilisé pour cet user<br/>

La commande qui permet d'afficher le man de ce fichier est man passwd<br/>

**Question 16 :** Affichez seulement la première colonne triée par ordre alphabétique inverse<br/>

La commande a entrée est : sort -r /etc/passwd<br/>

sort est la commande qui permet de trier et -r est l'équivalent de reverse.<br/>

**Question 17 :** Quelle commande nous donne le nombre d’utilisateurs ayant un compte sur cette machine (pas seulement les utilisateurs connectés) ?<br/>

la commande est : cut -d: -f1 /etc/passwd | wc -l<br/>

cut permet de couper le fichier -d: permet de dire chaque fois qu'il y a des : et le -f1 prend la première colonne La commande awk affiche les utilisateurs et la commande wc -l permet de compter.<br/>

**Question 18 :** Combien de pages de manuel comportent le mot-clé conversion dans leur description ?<br/>

A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine<br/>

find / -name passwd /usr/bin/passwd /usr/share/bash-completion/completions/passwd /usr/share/lintian/overrides/passwd /usr/share/doc/passwd /etc/passwd /etc/cron.daily/passwd /etc/pam.d/passwd /snap/core/7917/etc/cron.daily/passwd /snap/core/7917/etc/pam.d/passwd /snap/core/7917/etc/passwd /snap/core/7917/usr/bin/passwd /snap/core/7917/usr/share/bash-completion/completions/passwd /snap/core/7917/usr/share/doc/passwd /snap/core/7917/var/lib/extrausers/passwd<br/>

**Question 19 :** Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier \~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null find / -name passwd > list_passwd_files.txt 2> /dev/null

> : pour redir le stdout , ce qui s'affiche dans le terminal 2> : pour redir stderr, redirige les erreurs de la commande dans le fichier null.<br/>

**Question 20 :** Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment Utilisez la commande locate pour trouver le fichier history.log. Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ? Il n'apparaitra pas car il faut refresh ... avec la commande updatedb.<br/>

## Exercice 3 : Nano

F1 ou Ctrl + G Affichage de l’aide<br/>
Ctrl + X Quitter nano / Fermer une fenêtre / Exécuter une commande<br/>
Ctrl + R Ouvrir un fichier<br/>
Ctrl + O Enregistrer sous<br/>
Ctrl + S Enregistrer<br/>
Ctrl + K Couper<br/>
Ctrl + U Coller<br/>
Ctrl + W Rechercher<br/>
Ctrl + \ Remplacer<br/>
Ctrl + C Afficher des informations sur la position du curseur (numéro de ligne, de colonne)<br/>
Alt + U Annuler<br/>
Alt + E Refaire<br/>

## Exercice 5 : 

Plusieurs sites existe pour générer son propre prompt bash personnalisée : 

\--> <http://ezprompt.net/>

\--> <http://bashrcgenerator.com/>

voici le résultat obtenue : export PS1="\\\[\\e\[35m\\\]\[\\\[\\e\[m\\\]\\\[\\e\[35m\\\]\\A\\\[\\e\[m\\\]\\\[\\e\[35m\\\]\]\\\[\\e\[m\\\]-\\\[\\e\[92m\\\]\\u\\\[\\e\[m\\\]\\\[\\e\[92m\\\]@\\\[\\e\[m\\\]\\\[\\e\[92m\\\]\\h\\\[\\e\[m\\\]:\\\[\\e\[36m\\\]\\w\\\[\\e\[m\\\] "