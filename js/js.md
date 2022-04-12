# JavaScript [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript)

JavaScript (souvent abrégé en « JS ») est un langage de script léger, orienté objet, principalement connu comme le langage de script des pages web. Mais il est aussi utilisé dans de nombreux environnements extérieurs aux navigateurs web tels que [Node.js](https://nodejs.org/), [Apache CouchDB](https://couchdb.apache.org/) voire [Adobe Acrobat](https://www.adobe.com/devnet/acrobat/javascript.html).

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
let prenom = "Julia";

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
