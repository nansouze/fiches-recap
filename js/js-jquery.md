# jQuery [V3.6.0](https://jquery.com/download/)

Il existe une 2 types de versions:
- [compressed](https://code.jquery.com/jquery-3.6.0.min.js) -> code minifié, tout le code est à la suite sans saut de ligne.
- [uncompressed](https://code.jquery.com/jquery-3.6.0.js)

## Install

On peut installer jQuery de différentes manières:

### Npm

```sh

npm install jquery

```

### Yarn

```sh

yarn add jquery

```

### Bower

```sh

bower install jquery # uncompressed release

```

```sh

bower install https://code.jquery.com/jquery-3.6.0.min.js # compressed release

```

### CDN [Documentation](https://jquery.com/download/#using-jquery-with-a-cdn)

```html

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script> // Google CDN

```

### CodePen

**Methode 1:** On va dans l'engrenage `HTML` et on ajoute une balise `script` dans le `head`.


⚠️ **WARNING**
> On peut aussi ajouter jQuery avec CodePen.



```js

// DECLARATION
function direBonjour(prenom = "Bernard") {
    alert(`Bonjour ${prenom}`);
}

// APPEL
direBonjour(); // Bonjour Bernard

```
