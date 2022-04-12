# Boucles

## If / Else

```js

let age = 21;

if (age < 18) {
    console.log("Vous n'êtes pas majeur");
} else if (age < 21) {
    console.log("Vous êtes majeur en France");
} else {
    console.log("Vous êtes majeur partout, à vous les casinos !");
}

```

## Switch

```js

let produit = "chocolat";

switch(produit) {

    case "courgette":
    case "carotte":   
    case "pomme de terre":
        console.log('Ceci est un légume');
        break;
    
    case "banane":
        console.log('Ceci est un fruit');
        break;

    default:
        console.log('Ceci n\'est ni un fruit ni un légume');

}

```
