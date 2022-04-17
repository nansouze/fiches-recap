# Rest Parameter [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Functions/rest_parameters)

Cette syntaxe permet de représenter un nombre indéfini d'arguments sous forme d'un tableau.

```js

function addition(...nombres) {

    let resultat = 0;

    nombres.forEach(nombre => resultat += nombre);

    console.log(resultat);

}

addition(4, 9, 5, 415, 78, 54, 5);

```
