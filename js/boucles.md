# Boucles

## While

```js

let i = 1;

while (i < 5) {
    
    console.log('Ligne : ' + i);
    i++;

}

// Ligne : 1
// Ligne : 2
// Ligne : 3
// Ligne : 4

```

⚠️ **WARNING**
> Attention aux boucles infinies.

## Do While

```js

let prenom;

do {

    prenom = prompt('Quel est votre prénom ?');

} while (prenom == "" || prenom == null)

alert('Bonjour ' + prenom);

```

⚠️ **WARNING**
> A la différence de la boucle `while`, `do...while` s'éxécute au moins une fois.


## For

```js

for (let i = 1; i < 5; i++) {
    console.log('Ligne : ' + i);
}

```

⚠️ **WARNING**
> Ici, la boucle `for` fait la même chose que la boucle `while` au-dessus, mais en 3 lignes.

```js

let text = '';

for (let i = 0; i < 10; i++) {
  if (i === 3) {
    continue;
  }
  text = text + i;
}

console.log(text); // expected output: "012456789"

```

⚠️ **WARNING**
> l'instruction `continue` arrête l'exécution des instructions pour l'itération de la boucle courante ou de la boucle étiquetée. <br> L'exécution est reprise à l'itération suivante.


## For In (Object) [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/for...in)

```js

const object = { a: 1, b: 2, c: 3 };

for (const property in object) {
  console.log(`${property}: ${object[property]}`);
}

// "a: 1"
// "b: 2"
// "c: 3"

```

⚠️ **WARNING**
> Si l'on veut utiliser une boucle `for in` pour un tableau, il faut ruser avec l'index.

```js

const panier = ['fraise', 'banane', 'poire'];

for (const fruit in panier) {
  console.log(fruit); // 0 1 2
}

```

```js

const panier = ['fraise', 'banane', 'poire'];

for (const fruit in panier) {
  console.log(panier[fruit]); // fraise banane poire
}

```

## For Of (Array) [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Statements/for...of)

```js

const array1 = ['a', 'b', 'c'];

for (const element of array1) {
  console.log(element);
}

// "a"
// "b"
// "c"

```

## ForEach [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)

```js

const listeDePays = ['France', 'Belgique', 'Japon', 'Maroc'];

listeDePays.forEach(function(pays){
    console.log(pays);
});

listeDePays.forEach(pays => console.log(pays));

```
