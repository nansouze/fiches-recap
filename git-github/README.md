# Git & GitHub

## Git (Versionning & Collaboration)

<p align="center">
  <img src='img/Git.png'  width='20%'>
</p>

[Git](https://git-scm.com/) est un outil collaboratif de [gestion de version](https://fr.wikipedia.org/wiki/Gestion_de_versions), créé par Linus Torvalds. C'est un outil simple et performant, dont la principale tâche est de gérer l'évolution du contenu d'une arborescence (donc d'un site internet).

### Concepts Fondamentaux de Git

Pour un dossier de travail donné, Git manipule différents **espaces virtuels**:

| Espaces             | Description                           |
| :------------------ | :------------------------------------ | 
| `Workspace`         | espace stockant les modifications en cours, qui ne sont pas (encore) prises en compte par Git. |
| `Index (ou Stage)`  | espace stockant les modifications en cours, qui seront prises en compte par Git pour le prochain commit (mais pas encore commitées). |
| `Local Repository`  | espace stockant les modifications déjà prises en compte par Git. |
| `Remote Repository` | désigne le dépôt distant (remote, sur [GitHub](https://github.com/) par exemple), dépôt auquel est relié votre dépôt local. **Les commits du local repository doivent y être pushés pour mettre le dépôt distant à jour** et collaborer avec d'autres personnes. |

<p align="center">
  <img src='img/Git_Overview.png'  width='70%'>
</p>

## GitHub (Code Hosting Platform)

<p align="center">
  <img src='img/Git_Hub.png'  width='30%'>
</p>

Pour faciliter la communication autour du projet, les bons vieux emails fonctionnent, mais il existe aujourd'hui des sites et de services complémentaires à Git. Le site [GitHub](https://github.com/) est l'un d'entre eux.

[GitHub](https://github.com/) est une plateforme de services & un réseau social — [GitHub](https://github.com/) agit comme serveur central, permettant de partager son code dans un dépôt [Git](https://git-scm.com/) centralisé et partagé sur internet, mais également de communiquer avec d'autres développeurs par l'intermédiaire de commentaires, d'issues, etc.

[GitHub](https://github.com/) est probablement le réseau social de développeurs le plus populaire aujourd'hui.

<p align="center">
  <img src='img/Github_Social.png'  width='30%'>
</p>

Mais, il n'est pas le seul. Il existe également d'autres services comme:

- [GitLab](https://docs.gitlab.com/ee/user/project/repository/)
- [Bitbucket](https://bitbucket.org/)
