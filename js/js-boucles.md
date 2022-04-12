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

do {

    var prenom = prompt('Quel est votre prénom ?');

} while(prenom == "" || prenom == null)

alert('Bonjour ' + prenom);

}

```

⚠️ **WARNING**
> A la différence de la boucle `while`, `do...while` s'éxécute au moins une fois.
