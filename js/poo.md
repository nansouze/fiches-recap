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

## Création objet avec un constructeur personnalisé

```js

// On crée une fonction constructeur pour nos utilisateurs
function Utilisateur(prenom, nom, email) {
  this.prenom = prenom;
  this.nom    = nom;
  this.email  = email;
  
  this.sePresenter = () => {
    console.log("Bonjour, je m'appelle " + this.prenom + " " + this.nom + " et vous pouvez me contacter à l'adresse email " + this.email);
  }
}

// On crée un objet
var mark = new Utilisateur("Mark", "Zuckerberg", "mark@facebook.com");
var bill = new Utilisateur("Bill", "Gates", "bill@gatesnotes.com");

mark.sePresenter(); // "Bonjour, je m'appelle Mark Zuckerberg et vous pouvez me contacter à l'adresse email mark@facebook.com"
console.log(mark); // Objet mark

mark.poste = "PDG de Facebook";

console.log(mark); // Objet mark
console.log(bill); // Objet bill

function Logement(type, annee, placeDeParking, proprietaire) {
  this.type             = type;
  this.annee            = annee;
  this.placeDeParking   = placeDeParking;
  this.proprietaire     = proprietaire;
}

var appartementA = new Logement('Appartement', 2014, true, mark); // Mark est un objet

console.log(appartementA.proprietaire.prenom); // Mark
console.log(appartementA); //Objet ApartementA

```

## Prototypes (chaîne des prototypes)

```js

function Utilisateur(prenom, nom, email) {
  this.prenom = prenom;
  this.nom    = nom;
  this.email  = email;
}

Utilisateur.prototype.sePresenter = function() {
    console.log("Bonjour, je m'appelle " + this.prenom + " " + this.nom + " et vous pouvez me contacter à l'adresse email " + this.email);
}

// On crée un objet
var mark = new Utilisateur('Mark', 'Zuckerberg', 'mark@facebook.com');
var bill = new Utilisateur('Bill', 'Gates', 'bill@gatesnotes.com');

console.log(mark); // On voit que JavaScript ajoute une propriété __proto__ et constructor

mark.sePresenter();

// Créer un objet avec Object()
var monObjet = new Object();
monObjet.titre = "Le titre de l'objet";

```

⚠️ **WARNING**
> Le constructeur `Object`, nous permet de créer des objets génériques. Partage de méthodes & propriétés (Héritage).

> Il faut absolument utiliser une fonction anonyme (et pas flêchée, car pas de `this`) avec `prototype`.

## Héritage

```js

// Constructeur de base
function Animal(nombreDePattes, poids) {
  this.nombreDePattes = nombreDePattes;
  this.poids         = poids;
}
Animal.prototype.presentation = function() {
  console.log('Cet animal possède ' + this.nombreDePattes + ' pattes et fait ' + this.poids + '.');
}

// Constructeurs spécialisés
function Oiseau(nombreDePattes, poids, longueurDesAiles) {
  Animal.call(this, nombreDePattes, poids); // La fonction Call() permet d'appeler une fonction constructeur : en premier paramètre on donne l'objet actuel (this), ensuite, on donne les arguments pour son constructeur 
  this.longueurDesAiles = longueurDesAiles;
}
Oiseau.prototype = Object.create(Animal.prototype); // On change les informations en donnant un nouvel objet qui sera le prototype de notre constructeur animal
Oiseau.prototype.constructor = Oiseau; // On redéfinit la valeur de Oiseau.prototype.constructor car elle a été changée avec le changement de prototype

function Mammifere(nombreDePattes, poids, typeDePoils) {
  Animal.call(this, nombreDePattes, poids);
  this.typeDePoils = typeDePoils;
}
Mammifere.prototype = Object.create(Animal.prototype);
Mammifere.prototype.constructor = Mammifere;

var perroquet = new Oiseau(2, '1kg', 'grandes');
// console.log(perroquet.nombreDePattes);

perroquet.presentation();

```

## Bind, Call & Apply

```js

// Call et Apply permettent d'invoquer immédiatement une fonction
// Animal.call(this (l'objet en cours), nombreDePattes, poids)

// Call = Apply
var gandalf = { titre: "Magicien" };
function direBonjour() {
  console.log("Bonjour " + this.titre);
}
// direBonjour.call(gandalf);

// Apply != Call
var gandalf = { titre: "Magicien" };
let arme = ['un bâton', 75];

function direBonjour(arme, degats) {
  console.log("Bonjour " + this.titre + ", vous possédez " + arme + " qui donne " + degats + " points de dégats.");
}

direBonjour.call(gandalf, arme);
direBonjour.apply(gandalf, arme[0], arme[1]); // La seule différence : apply accepte les arguments nécessaire sous forme de tableau, à l'inverse call par variables

// Bind
// Objectif : Créer une nouvelle fonction, avec le même contexte et les mêmes propriétés que la fonction en paramètre (permet de changer le this)
// Surtout utilisé avec les fonctions anonymes à l'intérieur d'un objet

this.valeur = "Window";

let monObjet = {
  valeur: "Objet",
  getValeur: function() {
    console.log(this.valeur);
  }
}

monObjet.getValeur();

let maValeur = monObjet.getValeur;
maValeur(); // Window, car console.log(this.valeur) fait référence à l'objet global

// Pour corriger ce problème, on utilise bind, qui va récréer une fonction avec le contexte de l'objet monObjet

// let maValeurAvecBind = maValeur.bind(monObjet); // ici, on "prend" le contexte de base
let maValeurAvecBind = monObjet.getValeur.bind(monObjet); // Fait la même chose
maValeurAvecBind();

```

## Classes

```js

// class Utilisateur {
//   constructor(prenom, nom, email) {
//     this.prenom = prenom;
//     this.nom    = nom;
//     this.email  = email;
//   }
  
//   sePresenter() {
//     console.log("Je m'appelle " + this.prenom + ' ' + this.nom + " et vous pouvez me contacter à l'adresse email " + this.email + ".");
//   }
// }

// var mark = new Utilisateur('Mark', 'Zuckerberg', 'mark@facebook.com');
// mark.sePresenter();

class Animal {
  constructor(nombreDePattes, poids) {
    this.nombreDePattes = nombreDePattes;
    this.poids          = poids;
  }
  
  presentation() {
    console.log("Cet animal possède " + this.nombreDePattes + " pattes et fait " + this.poids + ".");
  }
}

class Oiseau extends Animal {
  constructor(nombreDePattes, poids, longueurDesAiles) {
    super(nombreDePattes, poids);
    this.longueurDesAiles = longueurDesAiles;
  }
  
  voler() {
    console.log("L'oiseau vole !");
  }
}

var perroquet = new Oiseau(2, "1kg", "grandes");
perroquet.presentation();
perroquet.voler();
console.log(perroquet);

```

## Getter & Setter

```js

class Utilisateur {
  constructor(prenom, nom, email) {
    this.prenom = prenom;
    this.nom    = nom;
    this.email  = email;
  }
  
  // Un getter (accesseur) permet de récupérer une propriété
  get nomComplet() {
    return this.prenom + ' ' + this.nom;
  }
  
  // Un setter (mutateur) permet de définir une propriété
  set nomComplet(valeur) {
    [this.prenom, this.nom] = valeur.split(' '); // split() divise une chaîne de caractère à partir d'un séparateur pour faire un tableau
  }
  
  sePresenter() {
    console.log("Je m'appelle " + this.prenom + ' ' + this.nom + " et vous pouvez me contacter à l'adresse email " + this.email + ".");
  }
}

var mark = new Utilisateur('Mark', 'Zuckerberg', 'mark@facebook.com');
console.log(mark.nomComplet);
mark.nomComplet = "Bill Gates";
console.log(mark.nomComplet);

// class Animal {
//   constructor(nombreDePattes, poids) {
//     this.nombreDePattes = nombreDePattes;
//     this.poids          = poids;
//   }
  
//   presentation() {
//     console.log("Cet animal possède " + this.nombreDePattes + " pattes et fait " + this.poids + ".");
//   }
// }

// class Oiseau extends Animal {
//   constructor(nombreDePattes, poids, longueurDesAiles) {
//     super(nombreDePattes, poids);
//     this.longueurDesAiles = longueurDesAiles;
//   }
  
//   voler() {
//     console.log("L'oiseau vole !");
//   }
// }

// var perroquet = new Oiseau(2, "1kg", "grandes");
// // perroquet.presentation();
// // perroquet.voler();
// console.log(perroquet);

```
