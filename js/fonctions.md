# Fonctions

## Déclaration & Appel

```js

// DECLARATION
function direBonjour() {
    alert("Hello World");
}

// APPEL
direBonjour();

```

## Paramètres

```js

// DECLARATION
function direBonjour(prenom) {
    alert(`Bonjour ${prenom}`);
}

// APPEL
direBonjour("Patrick");

```

⚠️ **WARNING**
> On peut mettre des paramètres par défaut.

```js

// DECLARATION
function direBonjour(prenom = "Bernard") {
    alert(`Bonjour ${prenom}`);
}

// APPEL
direBonjour(); // Bonjour Bernard

```

## Retourner une valeur

```js

let nombreUn = 4, nombreDeux = 7;

function addition(n1, n2) {
    const result = n1 + n2;
    return result;
}

addition(6,4); // 10

```

⚠️ **WARNING**
> `void` -> de base ne retourne pas de valeurs.

## Convertir nos données

```js

// STRING -> NUMBER
// age = parseInt(age);
// age = parseFloat(age);
// age = +age;
age = Number(age);

// NUMBER -> STRING
// nombre = 45;
// nombreEnString = nombre + "";
nombreEnString = nombre.toString();

```

⚠️ **WARNING**
> Il existe aussi des objets, avec des méthodes bien spécifiques.

```js

// OBJET MATH
let tailleAuCarre = Math.pow(taille, 2);

```

## Fonctions Anonymes

Une fonction anonyme est une fonction qui ne va pas posséder de nom. On utilise généralement ces fonctions lorsque nous n'avons pas besoin de les appeler par leur nom. C'est-à-dire, lorsque nous utilisons notre fonction immédiatement, sans la réutiliser plus tard. Il y a 3 façons de l'éxécuter:

- en l'utilisant dans une variable (souvent dans un objet)
- en l'auto-invoquant
- en utilisant un évènement (que nous verrons plus tard)

```js

// EXPRESSION
let fonctionAnonyme = function() {
    console.log('Je suis une fonction anonyme');
  }

// APPEL
fonctionAnonyme();

```

```js

// ici nous avons juste englobé notre fonction dans des paranthèses, et ajouté "()" à la fin
(function(){ console.log('Je suis une fonction anonyme') })(); 

```

## Fonctions Récursives

Une fonction peut faire référence à elle-même et s'appeler elle-même. [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Functions#la_r%C3%A9cursivit%C3%A9)

```js

// TIMER
function timer(secondes) {
    
    if (secondes > 0) {
        console.log(secondes);
        timer(secondes - 1);
    }
    else {
        console.log(0);
    }

}

timer(10); // 10 9 8 7 6 5 4 3 2 1 0

```

```js

// SOMME
function somme(nombre) {
    
    if(nombre == 1) {
        return 1;
    }

    return nombre + somme(nombre - 1);

}

console.log(somme(3)); // 3 + 2 + 1 -> 6

```

## Fonctions Fléchées


```js

// Dans la pratique, on l'utilise surtout pour les petites fonctions anonymes
// Nous verrons plus tard que ces fonctions fléchées n'ont pas de this

let maFonction = function(){
  console.log('test');
}

let maFonction = () => {
  console.log('test');
}

let maFonction = () => console.log('test');

```

## Closures


```js

function bonjour(prenom) {
  
  let resultat = "Bonjour " + prenom; // Variable locale
  let maClosure = () => console.log(resultat);
  return maClosure;
  
}

function bonjour_bis(prenom) {
  
  let resultat = "Bonjour " + prenom; // Variable locale
  console.log(resultat);
  
}

let maFonction = bonjour('Evan');
maFonction();
bonjour_bis('Nicolas');

```
