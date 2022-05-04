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