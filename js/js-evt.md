# Evénements [MDN](https://developer.mozilla.org/fr/docs/Web/Events)

## Ecouter

### Méthode 1: on... (ancien)

```html

// Au click on déclenche une popup
<a onclick="return confirm('Etes-vous sûr de vouloir supprimer cet article ?')" 
   href="https://believemy.com">Supprimer cet article
</a>

// Au passage sur le bouton, la couleur de fond change
<button onmouseover="document.body.style.backgroundColor='orange'" 
        onmouseout="document.body.style.backgroundColor='white'">Passez au-dessus de moi
</button>

```

⚠️ **WARNING**
> On peut aussi utiliser la fonction `concat` pour fusionner les tableaux.


```js

let total = aliments.concat(fruits); // ['chocolat', 'sucre', 'lait', 'fraise', 'banane', 'poire']

```

## Découper une chaîne de caractères en plusieurs éléments

```js

let phrase = "Bonjour !";
let phraseTableau = [...phrase];

console.log(phraseTableau); // ['B', 'o', 'n', 'j', 'o', 'u', 'r', ' ', '!']

```

## Sélectionner un élément, et stocker les autres dans une variable

```js

let devises = ['dollars', 'euro', 'yen'];

// Sans décomposition
// let premiereDevise = devises[0];
// let autres = [devises[1], devises[2]];

// Avec décomposition
let [premiereDevise, ...autres] = devises;

console.log(premiereDevise); // dollars
console.log(autres); // ['euro', 'yen']


```
