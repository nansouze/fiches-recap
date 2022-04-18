# DOM (Document Object Model) [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document_Object_Model)

## Accéder aux éléments du DOM

### getElementsByTagName [MDN](https://developer.mozilla.org/fr/docs/Web/API/Element/getElementsByTagName)

```js

let header = document.getElementsByTagName('header');

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

console.log(h1); // <h1>Bienvenue sur mon site</h1>

```


### querySelectorAll [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document/querySelectorAll)

```js

let p = document.querySelectorAll('p');

console.log(p); // NodeList(2)

```
