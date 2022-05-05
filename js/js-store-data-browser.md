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

⚠️ **WARNING**
> L'erreur `HttpOnly`: Pour créer un cookie, le serveur utilise une fonction qui possède, parfois, une option : `httpOnly`. Cette option interdit tout simplement la lecture / modification / suppression de ce cookie par JavaScript. Je vous rassure, si c'est vous qui programmez votre site, vous saurez à l'avance ce que vous faites. Mais il est bon de rappeler dans cette session que si vous mettez l'option `httpOnly` lorsque vous créez vos cookies via un autre langage de programmation (comme le PHP), votre cookie ne pourra pas être utilisé par JavaScript. __Maintenant, vous le savez !__

## LocalStorage & SessionStorage

```js

// LocalStorage = Stocké dans le navigateur même après qu'il soit fermé
// SessionStorage = Stocké dans le navigateur pendant la session

// Et les cookies ?

// setItem[clé], [valeur]) / getItem[clé] / removeItem[clé]
// clear() : supprimer tout
// key([index]) : obtenir la clef située à l'index donnée
// length : obtenir le nombre d'éléments stockés

if(localStorage.getItem('prenom')) {
  document.body.append('Bonjour ' + localStorage.getItem('prenom'));
}
else {
  let prenom = prompt('Quel est votre prénom ?');
  localStorage.setItem('prenom', prenom);
  document.body.append('Bonjour ' + prenom);
}
// localStorage.clear();

```
