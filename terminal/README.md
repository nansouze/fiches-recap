# Terminal

C'est l'interface graphique qui va vous permettre d'accèder au **SHELL**. (`Bash`, `Zsh` ...).

| OS          | Shell             |
| :---------- | :---------------- |
| `Linux`     | `Bash`, `Zsh` ... |
| `macOs`     | Jusqu'aux dernières version, le shell par défaut qui était utilisé, c'était `Bash`. <br> A partir de macOS Catalina, c'est maintenant `Zsh`. |
| `Windows`   | Vous n'avez ni `Bash`, ni `Zsh`. A la place, on a l'invite de commande (`cmd.exe`). <br> Celà nous permet d'éxécuter des commandes `DOS` et d'ouvrir un autre shell qui est `Powershell` mais avec des commandes complètement différentes de `Bash` & `Zsh`. |

## Avant de commencer

### Casse
Le **shell script** (ou le langage que vous utilisez dans le terminal) est un langage qui est sensible à la casse. C'est à dire que les majuscules et les minuscules sont considérés comme des caractères différents.

Par exemple `pwd` est une commande, alors que `PWD ou Pwd ou pWD...` n'est pas une commande (n'existe pas).

### Tilde `~`
Dans le terminal, la tilde représente le répertoire HOME de l'utilisateur (vous). Ce répertoire est celui dans lequel vous trouvez (la plupart du temps) les dossiers suivants  :

```sh

~ ls
Applications         Library                  
Desktop              Movies             
Documents            Music
Downloads            Pictures

```

### Autocompletion
Très utile. Les développeurs sont des flemmards, c'est pour ça qu'ils ont mis en place l'autocomplétion.
Le principe est d’appuyer sur la touche `tabulation` pendant la saisie, et l'ordinateur va compléter tout seul votre saisie **si il peut**.


## Commandes basiques

Elles vont nous permettre de naviguer dasn nos fichiers à l'aide du terminal.

### `pwd` - Print Working Directory
Elle sert à afficher le dossier dans lequel vous vous trouvez actuellement.

```sh

~ pwd
/Users/fsb

```

⚠️ **WARNING**

> Petite astuce, dans un terminal si on surligne un block de texte et qu'on appuie sur la molette de la souris, on va automatiquement coller ce que nous avions sélectionné.

<p align="center">
  <img src='assets/img/Pwd.png'  width='70%'>
</p>

### `ls` - Lister le contenu d'un répertoire

```sh

~ ls
Applications         Library                  
Desktop              Movies             
Documents            Music
Downloads            Pictures

```

⚠️ **WARNING**

> Par convention, les fichiers/dossiers qui commencent par . sont cachés. Pour les voir, il faut utiliser `ls -a`. (a -> pour all)

> Il est possible d'ajouter une mise en liste avec l'option `-l` soit : `ls -l` (permissions, propriétaire, date ...)

> On peut combiner les deux arguments `ls -la`

> Pour savoir si c'est un dossier, on voit au début `d`(directory). Si il y a un `-`, celà veut dire que c'est un fichier.

<p align="center">
  <img src='assets/img/Ls.png'  width='70%'>
</p>

### `clear` - Nettoyage du terminal

```sh

~ clear

```

### `reset` - Relance le terminal

```sh

~ reset

```

### `cd` - Change Directory

```sh

~ cd Pictures
~ cd ..
~ cd ../Music

```

## Jouer avec les fichiers & les dossiers

### `touch` - Créer un nouveau fichier

```sh

~ touch python.txt
~ touch Documents/readme.txt

```

### `mkdir` - Make Directory

```sh

~ mkdir Python
~ mkdir Documents/Python

```

### `open` - Ouvrir un fichier ou dossier

```sh

~ open . # le point, représente le dossier courant
~ open python.txt

```

### `mv` - Move (déplacer ou renommer)

```sh

~ mv python.txt ./Documents # déplacer

~ mv README.md readme.md # renommer

```

### `rm` - Remove (supprimez un fichier ou un dossier plein)

```sh

~ rm readme.md # suppression d'un fichier

```

⚠️ **WARNING**

> Il faut utiliser le flag `-r` (recursive) & `-f` (force) avec **précaution.**

```sh

~ rm -rf test # suppression récursive & forcée d'un dossier

```

<p align="center">
  <img src='assets/img/Rm_rf.png'  width='70%'>
</p>

### `rmdir` - Remove Directory (supprimer un dossier vide)

Cette commande sert à supprimer une dossier **vide**.
Son fonctionnement est le même que `mkdir` :
```shell
mint@mint ~ $ rmdir dossierASupprimer/
mint@mint ~ $ rmdir ../dossierASupprimer/
mint@mint ~ $ rmdir dossierExistant/dossierASupprimer/
```

### `cp` - Copiez vos fichiers ou vos dossier

Pour copier un fichier :
```shell
mint@mint ~ $ cp chemin/fichier.extension cheminDeDestination/
```

Pour copier un dossier, on ajoute le paramètre -R (copie récursive) :
```shell
mint@mint ~ $ cp -R chemin/monDossier/ cheminDeDestination/
```

## Régler les droits sur un fichier/dossier

### Permissions / Droits

Pour définir les droits, il faut déjà savoir les compter !

| Type      | Chiffre |
|:----------|:--------|
| Lecture   | 4       |
| Ecriture  | 2       |
| Exécution | 1       |

Et ensuite on fait la somme des chiffres pour déterminer les droits que l'ont souhaite.

Exemples :
- droits en lecture et écriture => `6`
- droits en lecture, écriture et exécution => `7`
- droits en lecture uniquement => `4`

### Utilisateurs

Ensuite, on peut déterminer les permissions pour 3 niveaux/types d'utilisateurs :
- l'utilisateur propriétaire du fichier/dossier
- le groupe d'utilisateurs lié au fichier/dossier
- tous les autres

Ainsi, on peut dire que le propriétaire a tous les droits `7`, le groupe lecture + exécution `5`, aucun droit pour tous les autres `0` => `750`

### La commande

`chmod 755 /var/www/html` :
- lecture+ecriture+execution pour le propriétaire du dossier _/var/www/html_
- lecture+execution pour le groupe du dossier _/var/www/html_
- lecture+execution pour tous les autres

`chmod -Rf 755 /var/www/html` :
- applique la commande précédente pour le dossier _/var/www/html_ mais aussi tous ses enfants
