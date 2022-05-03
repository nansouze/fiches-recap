# Evénements [MDN](https://developer.mozilla.org/fr/docs/Web/Events)

## Ecouter

### Méthode 1: on...

```html

// Au click on déclenche une popup
<a onclick="return confirm('Etes-vous sûr de vouloir supprimer cet article ?')" 
   href="https://believemy.com">Supprimer cet article
</a>

// Au passage sur le bouton, la couleur de fond change
<button onmouseover="document.body.style.backgroundColor='orange'" 
        onmouseout="document.body.style.backgroundColor='white'">Passez au-dessus de moi
</button>

```

⚠️ **WARNING**
> Cette méthode est vraiment ancienne.

### Méthode 2: propriétés JS

```html

<a href="#">Supprimer cet article</a>

<button>Passez au-dessus de moi</button>

```

```js

let a = document.querySelector('a');
let button = document.querySelector('button');

// a.onclick = function(){
//   if(confirm('Etes-vous sûr ?')) {
//     location.href="https://believemy.com"
//   }
// }

a.onclick = () => {
  if(confirm('Etes-vous sûr ?')) {
    location.href="https://believemy.com"
  }
}

button.onmouseover = () => {
  document.body.style.backgroundColor = 'orange';
}

button.onmouseout = () => {
  document.body.style.backgroundColor = 'white';
}

```

### Méthode 3: gestionnaire d'évènements

```html

<a href="#">Supprimer cet article</a>

<button>Passez au-dessus de moi</button>

```

```js

let a = document.querySelector('a');
let button = document.querySelector('button');

// on peut faire un console.log(e) pour avoir plus d'info
a.addEventListener('click', (e) => {
  if(confirm('Etes-vous sûr ?')) {
    location.href = "https://believemy.com";
  }
});

button.addEventListener('mouseover', () => {
  document.body.style.backgroundColor = 'orange';
});

function backgroundWhite() {
  document.body.style.backgroundColor = 'white';
}

button.addEventListener('mouseout', backgroundWhite);
button.addEventListener('mouseout', () => {
  document.body.style.fontFamily = 'arial';
});

// on peut remove un evt
button.removeEventListener('mouseout', backgroundWhite);

```

⚠️ **WARNING**
> Cette méthode est la plus flexible car elle utilise le gestionnaire d'évènements.

