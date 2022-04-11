# JavaScript

JavaScript (souvent abrégé en « JS ») est un langage de script léger, orienté objet, principalement connu comme le langage de script des pages web. Mais il est aussi utilisé dans de nombreux environnements extérieurs aux navigateurs web tels que [Node.js](https://nodejs.org/), [Apache CouchDB](https://couchdb.apache.org/) voire [Adobe Acrobat](https://www.adobe.com/devnet/acrobat/javascript.html).

### Ressources

- [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript)

## Où écrire du JavaScript

### En attributs

```html

<button onclick="alert('Click')">Click Me</button>

```

### Dans une balise


```html

<script>
window.addEventListener('load', function () {
  console.log('Cette fonction est exécutée une fois quand la page est chargée.');
});
</script>

```

### Dans un fichier séparé


```html

<script src="scripts/main.js"></script>


```
