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

### Boite de dialogue Alert

```js

// ALERT -> Afficher une information
window.alert('Hello World !');

```

### Boite de dialogue Confirm

```js

// CONFIRM -> Demander une confirmation
window.confirm('Souhaitez-vous confirmer ?')

// CONFIRM -> Avec une condition
if(window.confirm('Souhaitez-vous confirmer ?')) {
  // Oui
  window.alert('Ok');
}
else {
  // Non
  window.alert('Annulation');
}

```

### Boite de dialogue Prompt

```js

// PROMPT -> Demander des renseignements
const age = window.prompt("Entrez votre age:");

let answer = `Vous avez donc ${age} ans`;

window.alert(answer);

```

⚠️ **WARNING**
> Si l'utilisateur, n'ayant pas rempli le champ du formulaire, clique sur le boutton `Annuler` -> `null`, si c'est sur le bouton `OK` -> `chaine de caractère vide`.

## Navigator [MDN](https://developer.mozilla.org/fr/docs/Web/API/Navigator)

### Informations principales

```js

navigator.cookieEnabled // true
navigator.platform // MacIntel
navigator.language // fr-FR

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





