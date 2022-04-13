# Tableaux

## Créer

### Simple

```js

// let monTableau = new Array('un', 'deux', 'trois');
// let monTableau = Array('un', 'deux', 'trois');
let monTableau = ['un', 'deux', 'trois'];

```

### Plusieurs Dimensions

```js

// Ancienne version
let monTableau2D = new Array(
    Array('Mark', 'Jeff', 'Bill'),
    Array('Zuckerberg', 'Bezos', 'Gates')  
);

// Nouvelle version
let monTableau2D = [
    ['Mark', 'Jeff', 'Bill'],
    ['Zuckerberg', 'Bezos', 'Gates']
];

```

### Associatif

```js

let monTableauAssociatif = {
    'prenom' : 'Mark',
    'nom'    : 'Zuckerberg',
    'poste'  : 'PDG de Facebook'
};

```

## Accéder Element

## Index

```js

// Simple
monTableau[0]; // un

// Plusieurs Dimensions
monTableau2D[0][1]; // Jeff

// Associatif
monTableauAssociatif['poste']; // PDG de Facebook
monTableauAssociatif.poste // PDG de Facebook

```

### Length

```js

// Renvoie le nbr elts du tableau
monTableau.length; // 3

// Renvoie le dernier elt du tableau
monTableau[monTableau.length - 1]; // trois

```
