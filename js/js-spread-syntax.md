# Spread Syntax [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Spread_syntax)

```js

// Exemple 1 : fusionner plusieurs tableaux
let fruits = ['fraise', 'banane', 'poire'];
let aliments = ['chocolat', 'sucre', 'lait', ...fruits];

console.log(aliments); // ['chocolat', 'sucre', 'lait', 'fraise', 'banane', 'poire']

```

⚠️ **WARNING**
> On peut aussi utiliser la fonction `concat` pour fusionner les tableaux.


```js

let total = aliments.concat(fruits);

```
