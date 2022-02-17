# Les Selecteurs [MDN](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Selectors)

## Les Selecteurs Simples

`UNIVERSEL`

```css

* {
    font-weight: bold;
}

````

`TYPE`

```css

body {
  color: red;
}

````

`ID`

```css

/* L'élément avec l'identifiant id="demo" */

#demo {
  border: red 2px solid;
}

````

`CLASSE`

```css

/* Cible tous les éléments ayant la classe "spacious" */

.spacious {
  margin: 2em;
}

/* Cible tous les éléments <li> ayant la classe "spacious" */

li.spacious {
  margin: 2em;
}

/* Cible tous les éléments <li> ayant une classe qui */
/* contient à la fois "spacious" et "elegant"        */

li.spacious.elegant {
  margin: 2em;
}

````

`ATTRIBUT`

```css

a[href='https://example.org'] {
  color: green;
}

````

## Les Combinateurs

`VOISIN DIRECT`

```css

/* Ne cible que les paragraphes situé directement après une image */

img + p {
  font-weight: bold;
}

```

`VOISINS GENERAUX`

```css

/* Parmi tous les éléments <img>, cibler tous éléments <p> qui les suivent. */

img ~ p {
  color: red;
}

````

`DESCENDANT`

```css

/* Les éléments <li> qui sont des descendants */
/* d'un <ul class="mon-truc"> */

ul.mon-truc li {
  margin: 2em;
}

````