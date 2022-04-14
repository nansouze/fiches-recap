# Objets

## Créer

```js

let chien = {
    race: 'Shiba',
    poil: 'Court',
    aboyer: () => console.log('Wouaf Wouaf')
}

chien.aboyer();

```

## Affecter par décomposition (Destucturing) [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

```js

const o = {p: 42, q: true};
const {p, q} = o;

console.log(p); // 42
console.log(q); // true

```
