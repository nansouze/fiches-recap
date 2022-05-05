# Requêtes Asynchrones [MDN](https://developer.mozilla.org/fr/docs/Learn/JavaScript/Asynchronous/Introducing)

## Overview

### Déjà utilisé avec setTimeout & setInterval

```js

// Attention, code puissant

// let i = 0;

// console.log('Fonction commencée');

// while(i < 9999999999) {
//   i++;
// }

// console.log('Fonction terminée');

function direBonjour(){
   console.log('bonjour');
}

setTimeout(direBonjour, 3000);
console.log('test');

```

### Promesses

```js

// Les promesses (async et await)
// Objet qui représente l'état d'une opération asynchrone
// En cours / Honorée / Rompue
// Exemple : Discord(), app de discussion en ligne, permet de parler aussi par micro. Utilise l'asynchrone pour ne pas bloquer tant que vous n'acceptez pas l'utilisation du micro.

// const promesse = new Promise((resolve, reject) => {
//   // Tâches asynchrones
  
//   // Promesse honorée : appel de resolve()
  
//   // Promesse rompue : appel de reject()
// });

// Mais généralement, nous ne créerons presque jamais de promesse, car les API modernes qu'on pourrait utiliser les ont déjà créées pour nous. Elles renvoient donc souvent un objet promesse en résultat qu'on utilisera pour savoir si tout s'est bien passé.

function chargerScript(script) {
  return new Promise((resolve, reject) => {
    let element = document.createElement('script');
    element.src = script;
    document.head.append(element);
    element.onload = () => resolve('Fichier ' + script + ' chargé');
    element.onerror = () => reject(new Error('Operation impossible pour le script ' + script));
  });
}
// const promesse = chargerScript('test.js');

// // Renvoi une erreur car le fichier test.js n'existe pas
// promesse.then(
//   function(result) {
//     console.log(result);
//   },
//   function(error) {
//     console.log(error);
//   }
// );

// promesse.then(result => console.log(result), error => console.log(error)); // Même code, avec des fonctions fléchées

// On peut aussi passer directement par la fonction elle-même
chargerScript('test.js')
.catch(console.log);

```

### Async & Await (sucres syntaxiques)

```js

// Async et Await sont ce qu'on appelle des "sucres syntaxiques" : ils n'apportent pas de nouvelles fonctionnalités, mais permettent d'utiliser les promesses de façon plus intuitives.

// On place 'async' devant une fonction pour la forcer à retourner une promesse, et pouvoir utiliser 'await' dans celle-ci.

// Si on place le mot-clé 'await' devant une promesse, JavaScript est obligé d'attendre que celle-ci soit terminée. Si elle est rompue, alors, il génèrera une exception. Nous ne somme ainsi plus obligés d'utiliser then() et catch().

// async function direBonjour() {
  
//   const promesse = new Promise((resolve, reject) => {
//     setTimeout(() => resolve('Promesse honorée !'), 1500)
//   });
  
//   let resultat = await promesse; // On attend que la promesse soit honorée ou rejetée, un peu comme then(), mais de façon plus intuitive
//   console.log(resultat);
// }

// direBonjour();
// console.log('une autre tâche');

function chargerScript(script) {
  return new Promise((resolve, reject) => {
    let element = document.createElement('script');
    element.src = script;
    document.head.append(element);
    element.onload = () => resolve('Fichier ' + script + ' chargé');
    element.onerror = () => reject(new Error('Operation impossible pour le script ' + script));
  });
}

async function resultat(){
  try {
    const scriptA = await chargerScript('test.js');
    console.log(scriptA);
    const scriptB = await chargerScript('autre.js');
    console.log(scriptB);
  }
  catch(error) {
    console.log(error);
    // document.head.lastChild.remove();
  }
}

resultat();

```
