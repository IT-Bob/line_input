# line_input

La fonction permet l'édition d'une ligne de commande. L'utilisateur peut se déplacer dans celle-ci et l'éditer à l'endroit voulu.

La fonction `line_input` est prototypée de la manière suivante :

	char *line_input(char *prompt, t_list *history)

- La variable `prompt` est la chaîne représentant l'invite de commande du Shell.
- La variable `history` contient l'historique des précédentes commandes.

Ces deux variables peuvent être `NULL`.

Lorsque l'utilisateur appuie sur `entrée`, la fonction renvoie la commande tapée.

## Fonctionnalités

- [x] Édition de la ligne à l'emplacement du curseur
- [x] Déplacement du curseur
	- la gauche et la droite sur plusieurs lignes
	- vers le haut et le bas avec `Ctrl`-`haut/bas` 
- [x] Déplacement rapide de mot en mot
	+ `Ctrl-gauche` pour aller au mot précédent
	+ `Ctrl-droite` pour aller au mot suivant
- [x] Déplacement rapide en début ou fin de ligne
	+ `Ctrl-a`, `home` ou `fn`+`gauche` pour aller en début de ligne
	+ `Ctrl-e`, `end` ou `fn`+`droite` pour aller en début de ligne
- [x] Sélection de tout ou partie de la ligne
	+ [x] sélection lettre par lettre avec `Shift`-`gauche/droite`
	+ [x] sélection de mot en mot avec `Shift`-`Ctrl`-`gauche/droite`
	+ [x] sélection plus complète avec `Shift`-_`combinaison de touche de déplacement rapide`_
	+ [x] supprimer la sélection
	+ [ ] remplacer la sélection par un caractère
	+ [ ] copier la sélection 
	+ [ ] couper la sélection
	+ [ ] coller la précédente sélection
- [x] Navigation dans l'historique
	+ `Ctrl-p` ou `haut` pour voir les commandes précédentes
	+ `Ctrl-n` ou `bas` pour voir les commandes suivantes
- [x] Gestion de `Ctrl-d` : efface le caractère sous le curseur, quitte s'il n'y a plus de caractère et renvoie `exit`
- [x] Gestion de `Ctrl-c`
- [x] Invertion du caractère sous le curseur et du précédent avec `Ctrl-t`
- [x] Effacement de l'écran avec `Ctrl-l`

## Utilisation et compilation

*line_input* utilise des fonctions de la [Libft][] et a besoin de son header pour pouvoir être compilé. Il faut fournir au _Makefile_ le chemin vers le dossier le contenant à l'aide de la variable *LIBFT_INC*.

	$> make LIBFT_INC=../libft/includes all

Le programme devra être compilé avec la bibliothèque `termcap`.

## **Sources**

- [Opengroup.org - The Open Group Base Specifications Issue 7](http://pubs.opengroup.org/onlinepubs/9699919799/utilities/contents.html)
- [marionpatrick.free.fr - Manuel des manuels](http://marionpatrick.free.fr/man_html/html/index.html)

[Libft]: https://github.com/aguerin42/libft.git
