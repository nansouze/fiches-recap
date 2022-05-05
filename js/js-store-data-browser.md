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

// path - Permet de préciser sur lequel répertoire (dossier) est disponible le cookie
document.cookie = 'prenom=John; path=/admin';

// domain - Permet de préciser sur quel nom de domaine est disponible le cookie
document.cookie = 'prenom=John; path=/admin; domain=believemy.com';

let date = new Date(Date.now() + 31536000000); // on ajoute 1 an en ms
date = date.toUTCString(); // il faut une date UTC

// expires - Permet de donner une date UTC jusqu'à laquelle le cookie est disponible, après cette date, il expirera
document.cookie = 'prenom=John; path=/admin; domain=believemy.com; expires=' + date;

// max-age - Se substitue à expires, permet de donner une durée en millisecondes
// jusqu'à laquelle le cookie est disponible. Après cette date, il expirera
document.cookie = 'prenom=John; path=/admin; domain=believemy.com; max-age=31536000000';

// secure - Permet de n'autoriser l'utilisation du cookie que sur les sites sécurisés (https)
document.cookie = 'prenom=John; path=/admin; domain=believemy.com; max-age=31536000000; secure'; 

```
