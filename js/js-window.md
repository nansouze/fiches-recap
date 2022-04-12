# Window

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
