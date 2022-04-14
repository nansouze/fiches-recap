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

## Objet Set [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Set)

```js

let nombres = [10, 45, 75, 10, 24, 45];
// let monSet  = new Set(nombres);
// Set { 10, 45, 75, 24 }

let monSet = new Set();

monSet.add('70');
monSet.add(87);
monSet.delete(87);

console.log(monSet.size);

```

## Objet Map [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Map)

```js

let utilisateurs = new Map();

utilisateurs.set('Mark Zuckerberg', {
    email: 'mark@facebook.com',
    poste: 'PDG',
});

utilisateurs.set('Bill Gates', {
    email: 'bill@gatesnotes.com',
    poste: 'Sauver le monde',
});

// utilisateurs.delete('Bill Gates');

console.log(utilisateurs);

```

## Objet WeakSet [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/WeakSet)

```js

let voitureA = {
  constructeur: 'Tesla',
  modele: 'Cybertruck'
}
let voitureB = {
  constructeur: 'Renault',
  modele: 'Espace'
}

let voitures = new WeakSet([voitureA, voitureB]);
console.log(voitures);

```

## Objet WeakMap [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/WeakMap)

```js

let voitures = new WeakMap();

let index = {
    id: 1
}

let voitureA = {
    constructeur: 'Tesla',
    modele: 'Cybertruck'
}

voitures.set(index, voitureA);

// voitures.delete(index);
console.log(voitures);

```

⚠️ **WARNING**
> voici 2 fiches pour bien comprendre [lien 1](https://believemy.com/course/le-programme-rocket/62/4) & [lien 2](https://believemy.com/course/le-programme-rocket/62/9).



