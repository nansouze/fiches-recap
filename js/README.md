# JavaScript

JavaScript (souvent abrégé en « JS ») est un langage de script léger, orienté objet, principalement connu comme le langage de script des pages web. Mais il est aussi utilisé dans de nombreux environnements extérieurs aux navigateurs web tels que [Node.js](https://nodejs.org/), [Apache CouchDB](https://couchdb.apache.org/) voire [Adobe Acrobat](https://www.adobe.com/devnet/acrobat/javascript.html).

### Ressources

- [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript)

## Où écrire du JavaScript

### En attributs

```html

<button onclick="alert('Click')">Click Me</button>

```

### Dans une balise

```html

<script>
window.addEventListener('load', function () {
  console.log('Cette fonction est exécutée une fois quand la page est chargée.');
});
</script>

```

### Dans un fichier séparé


```html

<script src="scripts/main.js"></script>

```

## Variables

| Convention   | Content     |
| :----------- | :---------- | 
| `camelCase`  | myVarName   |
| `PascalCase` | MyVarName   | 
| `snake_case` | my_var_name | 
| `kebab-case` | my-var-name |

```js

// VAR (Globale)
var user = "John";

// LET (Locale & peut être ré-assignée)
var prenom = "Julia";

// CONST (Constante & ne peut être ré-assignée)
const HOURS_IN_DAY = 24;

```

⚠️ **WARNING**
> Variables Globales **VS** Variables Locales.

```js

let crie = "Toujours plus bas !"; // Globale

function crieDeGuerre() {
  
  let crie = "Toujours plus fort !"; // Locale
  console.log(crie);
  
}

crieDeGuerre();
console.log(crie);

```

## Types

```js

// NUMBER
console.log(typeof 42);

// STRING
console.log(typeof 'blubber');

// BOOLEAN
console.log(typeof true);

// UNDEFINED
console.log(typeof undeclaredVariable);

```

## Concaténation

```js

const prenom  = "Nicolas";
const nom     = "Dupont";

console.log("Bonjour " + prenom + ' ' + nom + ' !');

// Bonjour [prenom] [age] !

```

## Opérateurs

- [Truthy](https://developer.mozilla.org/fr/docs/Glossary/Truthy)
- [Falsy](https://developer.mozilla.org/fr/docs/Glossary/Falsy)

### Opérateurs Arithmétiques

| Caractère    |  Opération     |
| :----------- | :------------- | 
| `+`          | Addition       |
| `-`          | Soustration    | 
| `*`          | Multiplication | 
| `/`          | Division       |
| `%`          | Modulo         |
| `**`         | Exponentielle  |

### Opérateurs Incrémentation & Décrémentation

```js

result++; // incrémentation = ajoute 1
result--; // décrémentation = retire 1
result += 2; // incrémentation = ajoute 2
result -= 2; // décrémentation = retire 2

```

### Opérateurs Comparaison

| Signe        |  Définition                       |
| :----------- | :-------------------------------- | 
| `==`         | Egal à la valeur                  |
| `===`        | Egal à la valeur et au type       | 
| `!=`         | Différent de la valeur            | 
| `!==`        | Différent de la valeur et du type |
| `>`          | Supérieur                         |
| `<`          | Inférieur                         |
| `>=`         | Supérieur ou égal                 |
| `<=`         | Inférieur ou égal                 |

### Opérateurs Logiques

`C1 && C2` (ET logique)
| C1      | C2       | Résultat          |
| :------ | :------- | :---------------- |
| `true`  | `true`   | `true`            |
| `true`  | `false`  | `false`           |
| `false` | `true`   | `false`           |
| `false` | `false`  | `false`           |

⚠️ **WARNING**
> Si la première valeur est [truthy](https://developer.mozilla.org/fr/docs/Glossary/Truthy), l'opérateur `&&` renvoie le deuxième opérande.

```js

true && "chien" // renvoie "chien"

[] && "chien" // renvoie "chien"

```

`C1 || C2` (OU logique)
| C1      | C2       | Résultat          |
| :------ | :------- | :---------------- |
| `true`  | `true`   | `true`            |
| `true`  | `false`  | `true`            |
| `false` | `true`   | `true`            |
| `false` | `false`  | `false`           |

`!C1` (NON logique)
| C1      | Résultat          |
| :------ | :---------------- |
| `true`  | `false`           |
| `false` | `true`            |

### Opérateur Conditionnel Ternaire

```js

// [CONDITION] ? [TRUE] : [FALSE]
let x = 2;

(x > 3) ? console.log("X est supérieur à trois") : console.log("X est inférieur à trois");

```

### Opérateur de Coalescence des Nuls (Nullish Coalescing Operator)

C'est un opérateur logique qui renvoie son opérande de droite lorsque son opérande de gauche vaut `null` ou `undefined` et qui renvoie son opérande de gauche sinon.

```js

const foo = null ?? 'default string';
console.log(foo); // expected output: "default string"

const baz = 0 ?? 42;
console.log(baz); // expected output: 0

```

## Boites de dialogue

### Alert

```js

// ALERT -> Afficher une information
alert('Hello World !');

```

### Confirm

```js

// CONFIRM -> Demander une confirmation
confirm('Souhaitez-vous confirmer ?')

// CONFIRM -> Avec une condition
if(confirm('Souhaitez-vous confirmer ?')) {
  // Oui
  alert('Ok');
}
else {
  // Non
  alert('Annulation');
}

```


### Prompt

```js

// PROMPT -> Demander des renseignements
const age = prompt("Entrez votre age:");

let answer = `Vous avez donc ${age} ans`;

alert(answer);

```

## Fonctions

### Déclaration & Appel

```js

// DECLARATION
function direBonjour() {
    alert("Hello World");
}

// APPEL
direBonjour();

```

### Paramètres

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

### Retourner une valeur

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

### Convertir nos données

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

### Fonctions Anonymes

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

## Conditions

### If / Else

```js

let age = 21;

if (age < 18) {
    console.log("Vous n'êtes pas majeur");
} else if (age < 21) {
    console.log("Vous êtes majeur en France");
} else {
    console.log("Vous êtes majeur partout, à vous les casinos !");
}

```

### Switch

```js

let produit = "chocolat";

switch(produit) {

    case "courgette":
    case "carotte":   
    case "pomme de terre":
        console.log('Ceci est un légume');
        break;
    
    case "banane":
        console.log('Ceci est un fruit');
        break;

    default:
        console.log('Ceci n\'est ni un fruit ni un légume');

}

```
