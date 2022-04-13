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

## Accéder Elément

### Index

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

## Ajouter Elément

### Push (fin) & Unshift (début)

```js

// Simple
monTableau.push('quatre');
monTableau.unshift('zero');

// Plusieurs Dimensions
monTableau2D.push('test');
monTableau2D[0].push('test');
monTableau2D[1].unshift('test');

// Associatif (pas de push & unshift)
monTableauAssociatif['nationalite'] = 'Américaine';
monTableauAssociatif.nationalite = 'Américaine';

```

## Supprimer Elément

### Pop (fin) & Shift (début)

```js

// Simple
monTableau.pop();
monTableau.shift();

// Plusieurs Dimensions
monTableau2D.pop();
monTableau2D[0].pop();
monTableau2D[1].shift();

// Associatif (pas de pop & shift)
delete(monTableauAssociatif['nationalite']);
delete(monTableauAssociatif.nationalite);

```

## Trouver Index Elément

### Index Of

```js

monTableau.indexOf('deux')); // 1

```

⚠️ **WARNING**
> ne marche que pour les tableaux simples.

## Concaténer

### Join

```js

// Simple
monTableau.join(); // un,deux,trois
monTableau.join(' / '); // un / deux / trois

// Plusieurs Dimensions
monTableau2D.join(' / ') // Mark,Jeff,Bill / Zukerberg,Bezos,Gates
monTableau2D[0].join(' / ') // Mark / Jeff / Bill

```

⚠️ **WARNING**
> ne marche que pour les tableaux simples & plusieurs dimensions. Pour les tableaux associatifs, il faudra utiliser une boucle spéciale.

## La Fonction Ultime

### Splice

```js

// Simple
monTableau.splice(1, 0, 'random', 'pie'); // Attention à l'index pour l'insert

// Plusieurs Dimensions
monTableau2D.splice(2, 0, ['30', '45', '70']);

```

⚠️ **WARNING**
> ne marche que pour les tableaux simples & plusieurs dimensions.
