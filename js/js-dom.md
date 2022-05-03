# DOM (Document Object Model) [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document_Object_Model)

## Accéder aux éléments du DOM

### getElementsByTagName [MDN](https://developer.mozilla.org/fr/docs/Web/API/Element/getElementsByTagName)

```js

let header = document.getElementsByTagName('header');
// let header = document.getElementsByTagName('header')[0];

console.log(header); // HTMLCollection(1)

```

### getElementById [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document/getElementById)

```js

let logo = document.getElementById('logo');

console.log(logo); // <div id="logo">...</div>

```

### getElementsByClassName [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document/getElementsByClassName)

```js

let container = document.getElementsByClassName('container');

console.log(container); // HTMLCollection(1)

```

### querySelector [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document/querySelector)

```js

let h1 = document.querySelector('h1');
// let container = document.querySelector('.container');

console.log(h1); // <h1>Bienvenue sur mon site !</h1>

```

⚠️ **WARNING**
> On peut utiliser `tagName`, `#idName`, `.className`.

```js

// let body = document.querySelector('body');
document.body

```

⚠️ **WARNING**
> Pas besoin de selectionner `body`.

### querySelectorAll [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document/querySelectorAll)

```js

let p = document.querySelectorAll('p');

console.log(p); // NodeList(2)

```

## Modifier les éléments du DOM (propriétées)

### textContent [MDN](https://developer.mozilla.org/fr/docs/Web/API/Node/textContent)

```js

let h1 = document.querySelector('h1');
h1.textContent = "Hello World !";

```

### innerHTML [MDN](https://developer.mozilla.org/fr/docs/Web/API/Element/innerHTML)

```js

let h1 = document.querySelector('h1');
h1.innerHTML = "<div style='font-weight: normal'>Hello World !</div>";

```

⚠️ **WARNING**
> Pour en savoir plus, voici toutes [les propriétés existantes](https://developer.mozilla.org/fr/docs/Web/API/Element).

## Ajouter des éléments au DOM

### 1ere méthode (texte)

```js

// Ecrit juste un texte à la suite de votre contenu
document.write('test');

```

### 2e méthode (élément brut)

```js

// Ajouter un élément brut -> chaine de caractère
// On peut choisir ou ajouter l'objet
let h1 = document.querySelector('h1');
h1.append('test');

```

### 3e méthode (objet)

```js

// Créer un élément
let helloWorld = document.createElement('div');

// Le personnaliser
helloWorld.textContent = "Hello World !";

// L'ajouter à notre page
// document.body.append(helloWorld); (après)
// document.body.appendChild(helloWorld); (après)
// append VS appendChild -> on ne peut pas passer du texte dans appendChild, obligatoirement un objet

// document.body.insertBefore(helloWorld, document.querySelector('.container')); (avant)

document.querySelector('.container').prepend(helloWorld); (avant)

```

⚠️ **WARNING**
> On peut enchainer les éléments `document.body.append(header, menu, p);`.

## Supprimer des éléments du DOM

### Remove

```js

// let h1 = document.querySelector('h1');
// h1.remove();

document.querySelector('h1').remove();

```

## Modifier le style des éléments

### 1ere méthode (décomposée)

```js

let header = document.querySelector('header');
header.style.backgroundColor = '#ffbd69';

```

### 2e méthode (directe)

```js

document.querySelector('h1').style.color = '#111d5e';
document.querySelector('h1').style.textAlign = 'center';

```

### 3e méthode (avec une classe)

```js

document.querySelector('header').className = "ma_class";

```
