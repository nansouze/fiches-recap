# Responsive Design

## Media Queries

<p align="center">
  <img src='assets/img/Responsive_1.png'  width='100%'>
</p>

```css

/* MEDIA QUERIES */

/* Mobile Styles */
@media only screen and (max-width: 576px) {
  body {
    background-color: #F09A9D; /* Red */
  }
}

/* Tablet Styles */
@media only screen and (min-width: 577px) and (max-width: 991px) {
  body {
    background-color: #F5CF8E; /* Yellow */
  }
}

/* Desktop Styles */
@media only screen and (min-width: 992px) {
  body {
    background-color: #B2D6FF; /* Blue */
  }
}

/* Pour faire disparaitre un element -> display: none; */

```

<p align="center">
  <img src='assets/img/Responsive_2.png'  width='100%'>
</p>

## Unités

| Unité	    | Relative à                                                           | 
| :-------- | :------------------------------------------------------------------- | 
| `em`      |  la taille de la police de l'élément parent                          |
| `rem`     |  la taille de la police de l'élément racine (standard du navigateur) |
| `vh`      |  1% de la hauteur du viewport (la zone d'affichage)                  |
| `vw`      |  1% de la largeur du viewport (la zone d'affichage)                  |
