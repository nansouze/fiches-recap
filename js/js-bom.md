# BOM (Browser Object Model)

## Window [MDN](https://developer.mozilla.org/fr/docs/Web/API/Window)

### Ouvrir une fenêtre

```js

window.open('https://believemy.com');

```

### Redimensionner une fenêtre

```js

let fenetre = window.open('https://believemy.com', '', 'width=900, height=700'); // '' -> _self, _blank, _parent, _top

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

⚠️ **WARNING**
> Comme l'objet `window` est un objet global (à la base de tout), il n'est pas nécessaire de le taper à chaque fois.

### Boite de dialogue Alert

```js

// ALERT -> Afficher une information
alert('Hello World !');

```

### Boite de dialogue Confirm

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

### Boite de dialogue Prompt

```js

// PROMPT -> Demander des renseignements
const age = prompt("Entrez votre age:");

let answer = `Vous avez donc ${age} ans`;

alert(answer);

```

⚠️ **WARNING**
> Si l'utilisateur, n'ayant pas rempli le champ du formulaire, clique sur le boutton `Annuler` -> `null`, si c'est sur le bouton `OK` -> `chaine de caractère vide`.

## Navigator [MDN](https://developer.mozilla.org/fr/docs/Web/API/Navigator)

### Informations principales

```js

navigator.cookieEnabled; // true
navigator.platform; // MacIntel
navigator.language; // fr-FR

```

## History [MDN](https://developer.mozilla.org/fr/docs/Web/API/History)

### Page précédente

```js

history.back();

```

### Page suivante (si existante)

```js

history.forward();

```

## Location [MDN](https://developer.mozilla.org/fr/docs/Web/API/Location)

### Recharger une page

```js

location .reload();

```

### Rediriger

```js

location.href();

```

## Screen [MDN](https://developer.mozilla.org/fr/docs/Web/API/Window/screen)

### Informations principales

```js

screen.availWidth; // 1680px
screen.availHeight; // 1050px
screen.pixelDepth; // 30

```
