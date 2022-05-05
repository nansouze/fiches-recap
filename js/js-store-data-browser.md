# Stocker des données dans le navigateur

## Cookies

```js

// Créer un cookie
document.cookie = 'prenom=John';

// Afficher tous les cookies
// alert(document.cookie);

// Modifier un cookie
document.cookie = 'prenom=Mark';

// Supprimer un cookie
document.cookie = 'prenom=';

// Options

document.cookie = 'prenom=John; path=/admin';
document.cookie = 'prenom=John; path=/admin; domain=believemy.com';

let date = new Date(Date.now() + 31536000000); // on ajoute 1 an en ms
date = date.toUTCString(); // il faut une date UTC
document.cookie = 'prenom=John; path=/admin; domain=believemy.com; expires=' + date;

document.cookie = 'prenom=John; path=/admin; domain=believemy.com; max-age=31536000000';

document.cookie = 'prenom=John; path=/admin; domain=believemy.com; max-age=31536000000; secure'; // utilisable que sur les site https

```
