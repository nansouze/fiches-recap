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

## Objet Date [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Date)

### Récupérer la date actuelle

```js

// 1er janvier 1970 à minuit UTC (londres)

let dateActuelle = Date();
console.log(dateActuelle); // norme anglo-saxonne

let dateEnSecondes = Date.now();
console.log(dateEnSecondes);

```

### Utiliser objet Date

```js

let dateActuelle = new Date();
let dateEnSecondes = new Date(Date.now());
let datePrecise = new Date(2019, 11, 09, 22, 25);
// Au-dessus :
//   - annee (obligatoire)
//   - mois (obligatoire) qui commence par 0

//   - jour (facultatif) qui commence par 1
//   - heure (facultatif) qui commence par 0
//   - minute (facultatif) qui commence par 0
//   - secondes (facultatif) qui commence par 0
//   - millisecondes (facultatif) qui commence par 0

console.log(dateActuelle);
console.log(dateEnSecondes);
console.log(datePrecise);

```

### Getter & Setter disponibles

```js

let dateActuelle = new Date();

console.log(dateActuelle.getDay()); // jour de la semaine (0 pour dimanche, 6 pour samedi)
console.log(dateActuelle.getFullYear()); // année
console.log(dateActuelle.getDate()); // jour du mois

console.log(dateActuelle.getUTCDay());
// Renvoi la date pour l'heure UTC (donc de Londres)
// Les fonctions sont identiques, on ajoute simplement UTC

dateActuelle.setFullYear(2750);
console.log(dateActuelle.getFullYear());

```

### Transformer une date au format local

```js

let dateActuelle = new Date();

// toLocaleDateString = jour, mois, l'année
// toLocaleTimeString = l'heure
// toLocaleString     = jour, mois, l'année, l'heure
// ON CHOISI LES OPTIONS QU'ON VEUT

let dateLocale = dateActuelle.toLocaleString(navigator.language, {
  weekday: 'long', // short (3 premières lettres), narrow (première lettre), long (toutes les lettres)
  year: 'numeric', // numeric (xxxx), 2-digit (xx)
  month: 'long', // short, narrow, long, numeric
  day: 'numeric', // numeric, 2-digit
  hour: 'numeric', // ...
  minute: 'numeric',
  second: 'numeric'
});

console.log(dateLocale);

```

### Templates String avec les dates

```js

// Avant
// let prenom = "John";
// let bonjour = "Bonjour " + prenom;
// console.log(bonjour);

// Maintenant
let prenom = "John";
let bonjour = `Bonjour ${prenom}`;
console.log(bonjour);

// Avec les dates
let date = new Date().getFullYear();
let copyright = `${date} © Believemy`;
console.log(copyright);

// Ou encore plus pratique : des calculs
let aliments = { fruits: 5, legumes: 1, biscuits: 75 }
let panier = `Dans votre panier, vous avez ${aliments.fruits + aliments.legumes + aliments.biscuits} articles.`;
console.log(panier);

```
