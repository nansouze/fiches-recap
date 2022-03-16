# Commandes Git

- [Cheat Sheet Git](assets/pdf/Github_Git_Cheat_Sheet.pdf)
- [GitFlow, méthode de travail très efficace pour gérer les branches](https://www.atlassian.com/fr/git/tutorials/comparing-workflows/gitflow-workflow)
- [Apprendre Git par la pratique](https://learngitbranching.js.org/)
- [Git Explorer](https://gitexplorer.com/)

## Général

### `git --version` - Obtenir la version de git

```sh

# Renvoie la version installée de git
git --version
git version 2.35.1

```

### `git --help` - Obtenir de l'aide

```sh

# Renvoie la liste des commandes disponibles
git --help

# Idem pour une commande précise 
git [commande] -h

```

### `git config` - Configuration des outils

Cela va permettre de configurer les informations de l'utilisateur pour tous les dépôts locaux.

```sh

# Nom affiché dans les commits
git config --global user.name "John Wick"

```

```sh

# Email associé au commit (conseil: le même que celui du compte GitHub):
git config --global user.email "john.wick@lecroquemitaine.fr"

```

```sh

# Choix de l'éditeur de texte utilisé pour écrire les messages de commit:
git config --global core.editor nano # ou code pour Visual Studio Code, ou vim pour VIM etc.

```

```sh

# Utilisation de 'master' comme nom de la branche initiale.
# Pour configurer le nom de la branche initiale pour tous les nouveaux dépôts.
# 'master' -> 'main', 'trunk' & 'development'.
git config --global init.defaultBranch <nom>

# La branche nouvellement créée peut être rénommée avec:
git branch -m <nom>

```

```sh

# Activation des couleurs dans le résultat des commandes git
git config --global color.ui true

```

⚠️ **WARNING**

> Pour vérifier la configutation complète: `git config -l`. Cette commande va afficher tous les réglages actifs de `git`.

## Dépôt Local

### `git init` - Initialiser où Créer un dépôt
```sh

# Initialiser un dépot local
git init

# Créer un dépôt local à partir du nom spécifié
git init [nom-du-projet]

# Message généré après l'initialisation (dossier caché .git)
Initialized empty Git repository in C:/Users/fsb/Desktop/Projet/.git/

```

### `git status` - Vérifier l'état courant du dépot

```sh

# Récapitule l'état local (workspace et index) des fichiers du projet géré avec git
git status

```

**En rouge:**

<p align="center">
  <img src='assets/img/Git_Status.png'  width='70%'>
</p>

<p align="center">
  <img src='assets/img/Git_Status_2.png'  width='70%'>
</p>

**En vert:**

<p align="center">
  <img src='assets/img/Git_Status_1.png'  width='50%'>
</p>

### `git add` - Ajouter un fichier

```sh

# Modifications qui vont être comittées
git add <files>

# Différentes façon ajouter un fichier
git add Brief.txt
git add .
git add -A

# Pour unstage un fichier
git rm --cached Brief.txt

```

### `git commit -m` - Valider les modifications

```sh

# Modifications qui vont être comittées
git commit -m "Ceci est mon 1er commit"

```

### `git commit --amend` - Modifier son dernier commit

```sh

# Modification du dernier commit
git commit --amend

```

### `git log` - Historique des modifications

```sh

# Afficher tous les commits
git log

```

## Dépôt Distant (GitHub)

### Créer son 1er dépôt via l'interface de GitHub

<p align="center">
  <img src='assets/img/Repo_Create.png'  width='100%'>
</p>

<p align="center">
  <img src='assets/img/Repo_Create_2.png'  width='70%'>
</p>

### Créer son 1er dépôt via le terminal

```sh

echo "# mon-projet" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M master
git remote add origin https://github.com/nansouze/mon-projet.git
git push -u origin master

```

### Associer un dépôt local à un dépôt distant

```sh

git remote add origin https://github.com/nansouze/mon-projet.git
git branch -M master
git push -u origin master

```

### Récupérer un dépôt distant

```sh

# Télécharge un projet et tout son historique de versions (par défaut : nom du repo sur le remote)
git clone [url] [nom-du-projet]

```

### Changer git remote origin

```sh

git remote set-url origin [url]

```

### Envoyer & recevoir les mises à jour

```sh

# Envoyer
git push

# Recevoir
git pull

```
