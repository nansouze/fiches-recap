# Programmation Orientée Objet (POO) [MDN](https://developer.mozilla.org/fr/docs/conflicting/Learn/JavaScript/Objects#la_programmation_orient%C3%A9e_objet_avec_javascript)

## Objets Litéraux

```js

let mark = {
  prenom: "Mark", // propriété
  nom: "Zuckerberg",
  email: "mark@facebook.com",
  
  // À l'ancienne
  sePresenter: function(){
    console.log("Bonjour, je m'appelle " + this.prenom);
  }
}

mark.sePresenter(); // Bonjour, je m'appelle Mark

function recevoirLesCoordonnees() {
  return { latitude: 35, longitude: 139 }
}

let coordonnees = recevoirLesCoordonnees();
console.log(coordonnees.latitude); // 35
console.log(coordonnees.longitude); // 139

```

⚠️ **WARNING**
> On utilise les objets litéraux, pour transmettre des informations.
