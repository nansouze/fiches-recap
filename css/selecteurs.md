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

/* Les éléments <li> qui sont des descendants d'un <ul class="mon-truc"> */

ul.mon-truc li {
  margin: 2em;
}

````

## Les Pseudo-Classes

Les [pseudo-classes](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-classes) permettent de cibler des éléments selon une information d'état qui n'est pas stockée dans l'arbre du document.

`:hover`

```css

/* Cible n'importe quel élément <a> lorsque celui-ci est survolé */

a:hover {
  background-color: gold;
}

```

`:active`

```css

/* Ne cible <a> que lorsqu'il est activé par exemple quand on clique dessus */

a:active {
  color: red;
}

```

`:link`

```css

/* Cible les liens qui n'ont pas encore été visités */

a:link {
  color: red;
}

```

`:visited`

```css

a:visited {
  color: #4b2f89;
}

```

`:focus`

```css

/* Cible n'importe quel élément <input> uniquement lorsqu'il a le focus */

input:focus {
  color: red;
}

```

`:first-of-type`

```css

/* Cible le premier élément <p> d'un type donné parmi ses éléments voisins */

p:first-of-type {
  color: red;
}

```

`:last-of-type`

```css

/* Cible n'importe quel paragraphe qui est le dernier paragraphe de son élément parent */

p:last-of-type {
  color: lime;
}

```

`:nth-of-type`

```css

/* Sélectionne chaque élément de type <p> dont la position parmi l'ensemble des éléments de type <p>
descendants directement du même élément parent, est un multiple de 4. */

p:nth-of-type(4n) {
  color: lime;
}

```

`:root`

```css

/* Sélectionne l'élément racine du document */
/* Pour un document HTML, c'est <html> */

:root {
  background: yellow;
}

```

```css

/* On déclare nos variables au tout début de notre CSS */

:root {
  --mainColor: pink;
  --mainMargin: 15px 70px;
}

body {
  background: var(--mainColor);
  margin: var(--mainMargin);
}

```

## Les Pseudo-Elements

Les [pseudo-éléments](https://developer.mozilla.org/fr/docs/Web/CSS/Pseudo-elements) représentent des entités du document qui ne sont pas décrites en HTML.

`::before`

```css

/* On ajoute un coeur avant les liens */

a::before {
  content: "♥";
}

```

`::after`

```css

/* Ajoute une flèche après les liens */

a::after {
  content: "→";
}

```

`::first-line`

```css

/* Sélectionne la première ligne d'un élément <p> */

p::first-line {
  color: red;
  text-transform: uppercase;
}

```

`::first-letter`

```css

/* Sélectionne la première lettre d'un élément <p> */

p::first-letter {
  color: red;
  font-size: 130%;
}

```
