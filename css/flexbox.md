# Flexbox

`flexbox` pour Flexible Box, est une manière très puissante de réaliser une mise en page.

- [A Complete Guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Interneting is Hard Flexbox](https://www.internetingishard.com/html-and-css/flexbox/)

## Code

`Utiliser flexbox et définir la ligne principale`

```css

#flexbox {
    display: flex;
    flex-direction: row; /* ou column / column-reserve / row-reverse */
}

```

`Laisser les éléments se mettre les uns en-dessous des autres si le navigateur est trop étroit`

```css

#flexbox {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap; /* ou wrap-reverse / nowrap */
}

```

`Positionner les éléments horizontalement`

```css

#flexbox {
    display: flex;
    flex-direction: row;
    justify-content: center; /* ou flex-start / flex-end */
}

```

`Positionner les éléments verticalement`

```css

#flexbox {
    display: flex;
    flex-direction: row;
    align-items: stretch; /* ou flex-start / center / flex-end */
}

```

`Définir la taille de base des éléments`

```css

.element {
    flex-basis: 100px; /* si vide, le navigateur regarde si une taille
est déjà spécifiée, sinon l'élément prendra la largeur équivalente
à son contenu */
}

```

`Définir l'espace vide à incorporer à un élément, en terme de proportion`

```css

.element {
    flex-grow: 1; /* 1 veut dire que l'élément prend tout l'espace vide restant,
si la valeur vaut 2, il en prendra deux fois plus en terme de proportions que
les autres éléments, etc */
}

```

`Définir la réduction d'un élément, en terme de proportion`

```css

.element {
    flex-shrink: 0; /* cette valeur n'autorise pas l'élément à être réduit si le navigateur
est trop étroit, 1 le permet, plus la valeur est supérieur et plus l'élément se réduit en
proportion par rapport aux autres */
}

```

`Définir les trois propriétés précédentes en une seule propriété`

```css

.element {
    flex: 0 0 100px; /* on retrouve donc FLEX-GROW FLEX-SHRINK FLEX-BASIS */
}

```

## Poster

<p align="center">
  <img src='assets/img/Css_Flexbox_Poster.png'  width='100%'>
</p>
