# Exceptions

<p align="center">
  <img src='assets/img/Exceptions.png'  width='35%'>
</p>

## Try & Catch

```js

try {
    alert(hello);
} catch (error) {
    alert(`la variable Hello n'existe pas`); 
}

```

```js

// alert(error.name); // ReferenceError
// alert(error.message); // hello is not defined
// alert(error); // ReferenceError: hello is not defined
// alert(error.stack); // ReferenceError: hello is not defined at test.js:2:11
// console.error(error.stack); ReferenceError: hello is not defined at test.js:2:11 (en ROUGE dans la console)

```

## Throw New Error

```js

try {
    let recompense = prompt("Choisissez une récompense : épée, arc, haches");
    let degats;
    
    switch(recompense) {
      case 'épée':
        degats = 40;
        break;
      case 'arc':
        degats = 30;
        break;
      case'haches':
        degats = 20;
        break;
      default:
        throw new Error('Vous ne pouvez pas tricher.');
    }
    
    alert(`Vous avez choisi: ${recompense} -> ${degats} dégats`);

} catch(error) {
    alert(error);
} finally {
    alert('Fin du programme'); // s'éxécute à chaque fois
}

```

## Erreurs silencieuses

### Mode Strict [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Strict_mode)

```js

// Le mode strict : début
// "use strict";

prenom = "John";
console.log(prenom);

direBonjour();
addition(7, 1);

function direBonjour() {
  // "use strict";
  nom = "Doe";
  console.log(nom);
}

function addition(nombreA, nombreA) {
  "use strict";
  console.log(nombreA + nombreA);
}

```
