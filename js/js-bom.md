# BOM (Browser Object Model)

## Window [MDN](https://developer.mozilla.org/fr/docs/Web/API/Window)

### Ouvrir une fenêtre

```js

window.open('https://believemy.com');

```

### Redimensionner une fenêtre

```js

let fenetre = window.open('https://believemy.com', '', 'width=900, height=700');

function resize() {
    fenetre.resizeTo(700, 470);
}

```

### Fermer une fenêtre

```js

let fenetre = window.open('https://believemy.com', '', 'width=900, height=700');

function resize() {
    fenetre.close();
}

```
