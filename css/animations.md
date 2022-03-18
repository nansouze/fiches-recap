# Les Animations CSS [MDN](https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Animations/Using_CSS_animations)

## Création & Utilisation

`HTML`

```html

<!-- Bouton -->
<button>Mon Bouton</button>

```

`CSS`

```css

/* Bouton */

button {
  padding: 15px 30px;
  border: 0;
  font-size: 1.5em;
  /*   transition: color 1s; */
  cursor: pointer;
}

/* button:hover {
  color: red;
} */

/* Créer une animation */

@keyframes premiereAnimation {

  from {
    color: black;
  }  
  
  to {
    color: red;
    transform: scale(1.1);
  }
}

/* Utiliser une animation */

button:hover {
  animation: premiereAnimation 1s infinite alternate; /* Nom + Time + Durée Cycle + Sens Cycle */
}

```
