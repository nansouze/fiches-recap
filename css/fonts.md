# Fonts [MDN](https://developer.mozilla.org/fr/docs/Web/CSS/font-family)

```css

/* POLICES GENERIQUES
        serif, sans-serif, monospace, cursive, fantasy
*/

/* POLICES PRE-INSTALLEES
        Arial, Times New Roman, Georgia, Trebuchet MS, Impact
*/

```

## Google Fonts (CDN)

https://fonts.google.com/ propose une grande quantité de fonts facilement utilisables.

1. Selectionner au moins une font
2. `SELECT THIS STYLE` permet de choisir les styles voulus (si la font en possède plusieurs)
3. `EMBED` permet de choisir entre 2 modes d'insertion
    - `<link>` à placer dans le HTML
    - `@import` à placer dans le CSS
4. `font-family: ...` dans le CSS permet de définir l'usage de la font

⚠️ **WARNING**
> Un indicateur indiquant le temps de chargement, il est fortement recommandé d'y faire attention. Trop de fonts selectionnées  rendrait la page HTML longue à charger.

## Utiliser des fonts spécifiques

Dans certains cas de figure, il est nécessaire de générer nos propres fonts (sans passer par un CDN) :

- Font propriétaire
- Font indisponible
- CDN indisponible
- Présentation / Travail hors-ligne

Des plateformes comme [fontSquirrel](https://www.fontsquirrel.com/) en plus de proposer des fonts libres, mettent à disposition des outils de génération de font pour le web.

Dans le cas de [fontSquirrel](https://www.fontsquirrel.com/), le [Generator](https://www.fontsquirrel.com/tools/webfont-generator) permet à partir d'un ou plusieurs fichiers de font de générer un kit prêt à l'emploi pour le web.

1. Uploader des fonts dans le [Generator](https://www.fontsquirrel.com/tools/webfont-generator) 
2. Valider les options et télécharger le webFontKit proposé
3. Récupérer les fichiers nécessaire
    - Les fichiers de fonts (.woff/.woff2) vers un dossier `fonts/` dans le projet
    - Le code CSS `stylesheet.css` fournissant la déclaration du `@font-face` avec les informations de la font (dont le nom à utiliser)
    -  Modifier les chemins vers les fichiers de fonts dans le CSS
4. `font-family: ...` dans le CSS permet de définir l'usage de la font en relation avec le nom défini dans la déclaration `@font-face`
