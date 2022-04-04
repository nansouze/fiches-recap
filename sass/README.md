# SASS (Syntactically Awesome Style Sheets)

## Introduction

 - [SASS Basics](https://sass-lang.com/guide)

<p align="center">
  <img src='assets/img/Sass.png'  width='70%'>
</p>

## Installation

### Téléchargement
- [Releases](https://github.com/sass/dart-sass/releases/)

<p align="center">
  <img src='assets/img/Sass_Releases.png'  width='100%'>
</p>

Il suffit de télécharger le bon fichier en fonction de son OS et de glisser `dart-sass` par exemple dans `C:\Program Files`.

### Ajouter SASS à nos variables d'environnement [Documentation](https://katiek2.github.io/path-doc/)

1. Versions de Windows
   * Pour Windows 8 ou 10 -> Appuyer sur la touche `Windows` et chercher `Système (Panneau de configuration)`.
   * Pour Windows 7 -> Click droit sur icone ordinateur sur le bureau et cliquer sur propriétés.
2. Paramètres avancés du système
3. Variables d'environnement ...
4. En dessous de Variables système, trouver la variable `PATH` et cliquer sur Modifier. Sinon il faudra la créer en appuyant sur Nouvelle.
5. Ajouter votre répertoire en appuyant sur Nouveau.
6. Appuyer sur OK
7. Redémarrer le Terminal
8. Pour vérifier si tout est ok, il faut taper `sass --version`

## Utilisation

<p align="center">
  <img src='assets/img/Sass_Projet.png'  width='20%'>
</p>


```sh

# 1ere façon
sass assets/sass/defaut.scss assets/css/defaut.css

# 2e façon
sass --watch assets/sass/defaut.scss assets/css/defaut.css

# 3e façon (meilleure méthode)
sass --watch assets/sass:assets/css/

# 4e façon (meilleure méthode + argument pour mettre notre fichier css sur une ligne)
# --style -> -s (par défaut, expanded)
sass --watch assets/sass:assets/css/ -s compressed

```

## Variables

```css

$couleurPrincipale: orange;

body {
    background-color: white;
    color: $couleurPrincipale;
}

```

## Commentaires

```css

// Commentaire monoligne

/*
    Commentaire
    sur plusieurs lignes
    différentes
*/

```

## Opérations Mathématiques

```css

/*
    Opérateurs :
        + : addition
        - : soustraction
        * : multiplication
        / : division
        % : modulo (restant d'une division)
*/

html {
    font-size: 15px * 2;
}

```

## Imbrications

```css

header {
    background-color: $couleurPrincipale;
    color: white;
    padding: 15px;
    text-align: center;
    margin-bottom: 10px;

    ul {
        margin: 0; padding: 0;
        list-style: none;

        li {
            display: inline-block;
        }
    }

    nav {
        a {
            text-decoration: none;
        }
    }
}

// Imbrication des propriétés (nesting)
// N'oubliez pas les ":" :)

p {
  font: {
    family: arial;
    weight: bold;
    size: 2em;
  }
}

```

## Rôle Opérateur &

```css

nav {
    a {
        text-decoration: none;

        &:hover {
            color: red;
        }
    }
}

```

## Importation + Partials

```css

/* A mettre dans defaut.scss */ 
@use 'header';

```

⚠️ **WARNING**
> Pour ne pas générer la feuille de style `header.css` dans le dossier `assets/css`, on va utiliser les partials (feuilles de styles dédiées à être intégrées dans d'autres feuilles de style). On va ajouter un underscore devant le nom du fichier: `_header.scss`.

<p align="center">
  <img src='assets/img/Sass_Partials.png'  width='20%'>
</p>

## Regrouper toutes les variables

On va mettre toutes variables dans un partial `_variables.scss`

```css

/* A mettre dans defaut.scss */ 
@use 'header';

@import 'variables';

```

⚠️ **WARNING**
> Il faut d'abord utiliser `@use` avant d'utiliser `@import`.

## Héritage

On va faire hériter la classe `.message` à  `.succes` & `.erreur`

```css

/* message */ 
.message {
    color: white;
    border-radius: 10px;
    padding: 10px;
    margin: 5px;
}

/* succés */ 
.succes {
    @extend .message;
    background-color: green;
}

/* erreur */ 
.erreur {
    @extend .message;
    background-color: red;
}

```

## Mixins

On va pouvoir par exemple en plus de l'héritage, jouer sur un paramètre. Ex `$couleur`

```css

/* MIXINS */ 
@mixin message($couleur: white) {
    color: $couleur;
    border-radius: 10px;
    padding: 10px;
    margin: 5px;
}

/* succés */ 
.succes {
    @include message();
    background-color: green;
}

/* erreur */ 
.erreur {
    @include message();
    background-color: red;
}

/* notification */ 
.erreur {
    @include message(black);
    background-color: #f3f3f3;
}

```

⚠️ **WARNING**
> On peut utiliser les mixins pour afficher les valeurs pour les anciens navigateurs. Si on veut imbriquer des mixins dans des mixins, il faut faire attention à l'ordre. (ex: border-radius avant message.

```css

/* MIXINS */ 
@mixin border-radius($radiusA, $radiusB) {
    -webkit-border-radius: $radiusA $radiusB;
    -moz-border-radius: $radiusA $radiusB;
    -ms-border-radius: $radiusA $radiusB;
    border-radius: $radiusA $radiusB;
}

@mixin message($couleur: white) {
    color: $couleur;
    @include border-radius(5px, 5px);
    padding: 10px;
    margin: 5px;
}

/* succés */ 
.succes {
    @include message();
    background-color: green;
}

/* erreur */ 
.erreur {
    @include message();
    background-color: red;
}

/* notification */ 
.erreur {
    @include message(black);
    background-color: #f3f3f3;
}

```
