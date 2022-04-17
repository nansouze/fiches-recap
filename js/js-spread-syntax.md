# Spread Syntax [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

## Fusionner plusieurs tableaux

```js

let fruits = ['fraise', 'banane', 'poire'];
let aliments = ['chocolat', 'sucre', 'lait', ...fruits];

console.log(aliments); // ['chocolat', 'sucre', 'lait', 'fraise', 'banane', 'poire']

```

⚠️ **WARNING**
> On peut aussi utiliser la fonction `concat` pour fusionner les tableaux.


```js

let total = aliments.concat(fruits);

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
