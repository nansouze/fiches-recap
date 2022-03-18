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

## Anciens Navigateurs

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

/* Ancien Navigateur */

@-webkit-keyframes premiereAnimation {

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
  -webkit-animation: premiereAnimation 1s infinite alternate; /* Ancien Navigateur */
}

```

⚠️ **WARNING**
> Ne pas oublier d'utiliser le préfixe `-webkit` devant `animation` & `@keyframes`.

## Créer des Etapes Intermédiaires

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

  0% {
    color: black;
  }
  
  50% {
    color: blue;
  }
  
  100% {
    color: red;
    transform: scale(1.1);
  }
}

/* Utiliser une animation */

button:hover {
  animation: premiereAnimation 1s infinite alternate; /* Nom + Time + Durée Cycle + Sens Cycle */
}

```

## Propriétés Non-Raccourcies

`CSS`

```css

animation-name: premiereAnimation;
animation-duration: 1s;
animation-delay: 4s;
animation-iteration-count: infinite; /* 4 */
animation-direction: alternate;

```

## Générer des Animations

- [Animista](https://animista.net/)
- [Keyframes.app](https://keyframes.app/)
