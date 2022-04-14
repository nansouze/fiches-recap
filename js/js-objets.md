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

⚠️ **WARNING**
> marche aussi avec les tableaux.

```js

const toto = ["un", "deux", "trois"];

// sans utiliser la décomposition
const un    = toto[0];
const deux  = toto[1];
const trois = toto[2];

// en utilisant la décomposition
const [un, deux, trois] = toto;


```
