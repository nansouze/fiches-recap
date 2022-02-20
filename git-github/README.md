# Git (Versionning & Collaboration)

<p align="center">
  <img src='img/Git.png'  width='20%'>
</p>

[Git](https://git-scm.com/) est un outil collaboratif de [gestion de version](https://fr.wikipedia.org/wiki/Gestion_de_versions), créé par Linus Torvalds. C'est un outil simple et performant, dont la principale tâche est de gérer l'évolution du contenu d'une arborescence (donc d'un site internet).

## Concepts Fondamentaux de Git

Pour un dossier de travail donné, Git manipule différents **espaces virtuels**:

| Espaces             | Description                           |
| :------------------ | :------------------------------------ | 
| `Workspace`         | espace stockant les modifications en cours, qui ne sont pas (encore) prises en compte par Git. |
| `Index (ou Stage)`  | espace stockant les modifications en cours, qui seront prises en compte par Git pour le prochain commit (mais pas encore commitées). |
| `Local Repository`  | espace stockant les modifications déjà prises en compte par Git. |
| `Remote Repository` | désigne le dépôt distant (remote, sur [GitHub](https://github.com/) par exemple), dépôt auquel est relié votre dépôt local. **Les commits du local repository doivent y être pushés pour mettre le dépôt distant à jour** et collaborer avec d'autres personnes. |

<br>

<p align="center">
  <img src='img/Git_Overview.png'  width='70%'>
</p>

## Créer une Clé SSH pour GitHub

Avant toute chose, pour utiliser [Git](https://git-scm.com/) et [GitHub](https://github.com/) à leur pleins potentiels, on va créer une clé dite SSH. Cette clé est une carte d'identité nous permettant de nous authentifier auprès de [GitHub](https://github.com/), notamment pour accéder aux repos privés, signer nos commits, etc.

- [Connecting to GitHub with SSH](https://help.github.com/articles/connecting-to-github-with-ssh/) 

### Vérification de Clés Existantes

Avant de générer une clé SSH, on peut vérifier si nous n'avons pas déjà de clés existantes.

```sh

# Affiche les fichiers du répertoire .ssh, si ils existent
$ ls -al ~/.ssh

```

Par défaut, les noms de fichier des clès publiques supportées pour GitHub sont les suivantes: 
- `id_rsa.pub`
- `id_ecdsa.pub`
- `id_ed25519.pub`

### Création de la Clé

```sh

# Attention à bien remplacer l'email par le votre ;)
$ ssh-keygen -t ed25519 -C "your_email@exemple.fr"

```

⚠️ **WARNING**

> Si votre système ne supporte pas Algorithme Ed25519, il faudra utiliser ce code:

```sh

# Attention à bien remplacer l'email par le votre ;)
$ ssh-keygen -t rsa -b 4096 -C "votre-email@exemple.fr"

```

> Il vous sera demandé d'inventer **une passphrase**, c'est-à-dire un mot de passe un peu costaud (qui peut carrément être une phrase, avec des espaces, des accents et tout ! Cette passphrase n'est pas strictement obligatoire (elle peut être vide…), mais il est fortement recommandé d'en choisir une. Par contre, il faut la retenir par cœur, si elle est perdue, **la clé SSH est bonne à jeter !**

Une clé SSH se compose de **deux parties**, si bien qu'à l'issue de la commande, vous obtenez deux choses:

- une **clé privée** dans `/home/mint/.ssh/id_rsa` — pour protégér du contenu, à garder pour soi !
- une **clé publique** dans `/home/mint/.ssh/id_rsa.pub` — elle est capable de lire du contenu protégé par la clé privé

<p align="center">
  <img src='img/Cles_Prive_Publique.png'  width='30%'>
</p>

### Ajout de la Clé Publique sur GitHub

Vous allez donc copier le contenu de la clé publique sur [GitHub](https://github.com/). Vous pouvez regarder le contenu de la clé publique, par curiosité:

```sh

# Pour récupérer le contenu de notre clé publique
cat ~/.ssh/id_rsa.pub

```

Copiez ce contenu, et allez le coller dans votre compte [GitHub](https://github.com/):

```sh

Settings > SSH and GPG keys > New SSH key > Coller le contenu de la clé et valider

```

⚠️ **WARNING**

> Pour que Git utilise automatiquement **la clé SSH** pour authentifier les commandes git ..., il faut utiliser des URLs avec le protocole `SSH` plutôt que `HTTPS`. [Why is GIT always asking for my password?](https://help.github.com/articles/why-is-git-always-asking-for-my-password/)

## Mémo Commandes GIT

- [Cheat Sheet Git](assets/Github_Git_Cheat_Sheet.pdf)
- [GitFlow, méthode de travail très efficace pour gérer les branches](https://www.atlassian.com/fr/git/tutorials/comparing-workflows/gitflow-workflow)

## Fichiers Spéciaux

| Nom       | Description                                                           |
| :-------- | :-------------------------------------------------------------------- |
| `.gitignore` | permet de lister des fichiers qui doivent être ignorés lors du add |
| `.gitkeep`   | est un fichier qui peut être placé à la racine d'un répertoire vide afin que git prenne ce dossier en compte même s'il ne contient pas de fichier |

# GitHub (Code Hosting Platform)

<p align="center">
  <img src='img/Git_Hub.png'  width='30%'>
</p>

Pour faciliter la communication autour du projet, les bons vieux emails fonctionnent, mais il existe aujourd'hui des sites et de services complémentaires à Git. Le site [GitHub](https://github.com/) est l'un d'entre eux.

C'est une plateforme de services & un réseau social — Il agit comme un serveur central, permettant de partager son code dans un dépôt [Git](https://git-scm.com/) centralisé et partagé sur internet, mais également de communiquer avec d'autres développeurs par l'intermédiaire de commentaires, d'issues, etc.

[GitHub](https://github.com/) est probablement le réseau social de développeurs le plus populaire aujourd'hui.

<p align="center">
  <img src='img/Github_Social.png'  width='50%'>
</p>

Mais, il n'est pas le seul. Il existe également d'autres services comme:

- [GitLab](https://docs.gitlab.com/ee/user/project/repository/)
- [Bitbucket](https://bitbucket.org/)
