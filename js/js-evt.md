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

### Méthode 2: propriétés JavaScript

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


## Gérer la propagation des évènements et stopPropagation

```html

<article style="background-color: silver">
  <h1 style="display: inline">Titre de l'article</h1>
</article>

```

```js

let article = document.querySelector('article');
let h1      = document.querySelector('h1');

article.addEventListener('click', () => {
  alert('article cliqué');
});

h1.addEventListener('click', (e) => {
  alert('titre cliqué');
  e.stopPropagation(); // On stop la propagation
});

```

⚠️ **WARNING**
> On utilise ``stopPropagation` sur évènement pour éviter les 2 popups.

## Planifier l'éxécution d'un script (setTimeout, setInterval)

```js

// setTimeout
let timer = setTimeout("alert('Bonjour')", 3000);
clearTimeout(timer);

// setInterval
let interval = setInterval("alert('Bonjour')", 5000);
clearInterval(interval);

```

## Principaux évènements

### Les écouteurs "on" et les propriétés JavaScript

| Evènement    | Action                                                              |
| :----------- | :------------------------------------------------------------------ | 
| `onfocus`    | Quand l'utilisateur sélectionne l'élément                           |
| `onchange`   | Quand l'utilisateur change la valeur de l'élément                   |
| `onclick`    | Quand l'utilisateur clique sur l'élément                            |
| `ondblclick` | Quand l'utilisateur double-clique sur l'élément                     |
| `onkeypress` | Quand l'utilisateur appuie sur une touche du clavier dans l'élément |

### Les évènements avec addEventListener

| Evènement    | Action                                                              |
| :----------- | :------------------------------------------------------------------ | 
| `click`      | Quand l'utilisateur clique sur l'élément                            |
| `mouseover`  | Quand l'utilisateur passe avec sa souris au-dessus d'un élément     |
| `mouseout`   | Quand l'utilisateur sort avec sa souris d'un élément                |
| `copy`       | Quand l'utilisateur copie un élément                                |
| `cut`        | Quand l'utilisateur coupe un élément                                |
| `paste`      | Quand l'utilisateur colle un élément                                |
