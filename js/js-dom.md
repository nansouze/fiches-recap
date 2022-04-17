# DOM (Document Object Model) [MDN](https://developer.mozilla.org/fr/docs/Web/API/Document_Object_Model)

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
