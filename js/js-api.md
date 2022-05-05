# API (Application Programming Interface) [MDN](https://developer.mozilla.org/fr/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)

## Utiliser une API

### Récupérer le prix du bitcoin (XMLHttpRequest)

`HTML`

```html

<div class="container">
  
  <div class="row justify-content-center">
    
    <div class="col-md-8">
      <h1 class="text-center mt-5">Bitcoin Price</h1>
      
      <div id="price" class="text-center">
        <span id="price_label">xxxx.xx</span> €
      </div>
    </div>
    
  </div>
  
</div>

```

`CSS`

```css

h1 {
  color: #272343;
}

#price {
  font-size: 4em;
}

```

`JS`

```js

// URL
const url = 'https://blockchain.info/ticker';

function recupererPrix() {
  // Créer une requête
  let requete = new XMLHttpRequest(); // Créer un objet
  requete.open('GET', url); // Premier paramètre GET / POST, deuxième paramètr : url
  requete.responseType = 'json'; // Nous attendons du JSON
  requete.send(); // Nous envoyons notre requête

  // Dès qu'on reçoit une réponse, cette fonction est executée
  requete.onload = function() {
    if (requete.readyState === XMLHttpRequest.DONE) {
      if (requete.status === 200) {
        let reponse = requete.response; // on stock la réponse
        let prixEnEuros = reponse.EUR.last;
        document.querySelector('#price_label').textContent = prixEnEuros;
      }
      else {
        alert('Un problème est intervenu, merci de revenir plus tard.');
      }
    }
  }
  console.log('Prix actualisé');
}

setInterval(recupererPrix, 1000);

```

### Envoyer des données

```js

// URL
const url = 'https://lesoublisdelinfo.com/api.php';

let requete = new XMLHttpRequest();

// Get
// requete.open('GET', url);
// requete.responseType = 'json';
// requete.send();

// Post
requete.open('POST', url);
requete.setRequestHeader('Content-Type', 'application/x-www-form-urlencoded');
requete.responseType = 'json';
requete.send('prenom=John'); // Pour envoyer plusieurs paramètre -> requete.send('prenom=John&nom=Doe');

requete.onload = function() {
  if (requete.readyState === XMLHttpRequest.DONE) {
    if (requete.status === 200) {
      let reponse = requete.response;
      console.log(reponse);
    }
    else {
      alert('Un problème est intervenu, merci de revenir plus tard.');
    }
  }
}

```

## Amélioration avec Fetch

### Récupérer le prix du bitcoin (Fetch)

```js

// URL
const url = 'https://blockchain.info/ticker';

async function recupererPrix() {
 
  const requete = await fetch(url, {
    method: 'GET'
  });
  
  if(!requete.ok) {
    alert('Un problème est survenu.');
  } else {
    let donnees = await requete.json();
    console.log(donnees);
    // document.querySelector('span').textContent = donnees.EUR.last;
  }
}

setInterval(recupererPrix, 1000);

```

### Envoyer des données (Fetch)

```js

// URL
const url = 'https://lesoublisdelinfo.com/api.php';

async function envoyerPrenom(prenom) {
  const requete = await fetch(url, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded'
    },
    body: new URLSearchParams({
      prenom // prenom: prenom
    })
  });
  
  if(!requete.ok) {
    alert('Un problème est survenu.');
  }
  else {
    let donnees = await requete.json();
    console.log(donnees);
  }
}

envoyerPrenom('Elon');

```

⚠️ **WARNING**
> `PUT` -> remplacer toute la donnée, `PATCH` -> modifier une partie la donnée, `DELETE` -> supprimer la donnée.

## Amélioration avec Axios

### Récupérer le prix du bitcoin (Axios)

```js

// URL
const url = 'https://blockchain.info/ticker';

async function recupererPrix() {
 
  const requete = await fetch(url, {
    method: 'GET'
  });
  
  if(!requete.ok) {
    alert('Un problème est survenu.');
  } else {
    let donnees = await requete.json();
    console.log(donnees);
    // document.querySelector('span').textContent = donnees.EUR.last;
  }
}

setInterval(recupererPrix, 1000);

```

### Envoyer des données (Axios)

```js

// URL
const url = 'https://lesoublisdelinfo.com/api.php';

async function envoyerPrenom(prenom) {
  const requete = await fetch(url, {
    method: 'POST',
    headers: {
      'Content-Type': 'application/x-www-form-urlencoded'
    },
    body: new URLSearchParams({
      prenom // prenom: prenom
    })
  });
  
  if(!requete.ok) {
    alert('Un problème est survenu.');
  }
  else {
    let donnees = await requete.json();
    console.log(donnees);
  }
}

envoyerPrenom('Elon');

```
