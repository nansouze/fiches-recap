# Médias

## Les Images

### Ajouter Image

```html

<img src="/img/logo-660-480.jpg" alt="Logo">

```

### Les Figures

La figure, sa légende et son contenu sont référencés comme une seule unité.

```html

<figure>
    <img src="/img/logo-660-480.jpg"
         alt="Logo">
    <figcaption>Ceci est mon logo</figcaption>
</figure>

```

### Les Favicons (ou Icônes) `<head>`

```html

<link rel="shortcut icon" href="favicon.png" type="image/png">

```

ou

```html

<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">

```

## Video [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/video)

| Attributs  | Définition                                             |
| :--------- | :----------------------------------------------------- |
| `controls` | offre une interface pour gérer la lecture et le volume |
| `autoplay` | permet de lancer la lecture automatiquement            |
| `loop`  | lit le fichier en boucle                                  |
| `muted` | mute le volume                                            |
| `poster` | permet de préciser une vignette pour la vidéo            |

L'élément `<source>` et son attribut `src` permet de spécifier une source, `type` précise de quel type  MIME est le fichier.

`HTML`

```html
<video controls="controls">
  <source src="podcast-eiffel.mp4" type="video/mp4">
  La vidéo n'est pas prise en charge <!-- Message en cas de fonctionnalité non supportée -->
</video>
```

Plusieurs `<source>` peuvent être ajoutées pour maximiser la compatibilité avec les différents navigateurs

> Plus d'informations sur [les formats pris en charge](https://developer.mozilla.org/fr/docs/Web/HTML/Formats_pour_audio_video) et un [guide d'utilisation](https://developer.mozilla.org/fr/docs/Web/HTML/Utilisation_d'audio_et_video_en_HTML5) complet sont disponibles sur MDN

## Audio [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/audio)

| Attributs  | Définition                                             |
| :--------- | :----------------------------------------------------- |
| `controls` | offre une interface pour gérer la lecture et le volume |
| `autoplay` | permet de lancer la lecture automatiquement            |
| `loop`     | lit le fichier en boucle                               |


L'élément `<source>` et son attribut `src` permet de spécifier une source, `type` précise de quel type  MIME est le fichier.

`HTML`

```html
<audio controls="controls">
  <source src="podcast-eiffel.mp3" type="audio/mp3">
  L'audio n'est pas pris en charge <!-- Message en cas de fonctionnalité non supportée -->
</audio>
```

Plusieurs `<source>` peuvent être ajoutées pour maximiser la compatibilité avec les différents navigateurs

> Plus d'informations sur [les formats pris en charge](https://developer.mozilla.org/fr/docs/Web/HTML/Formats_pour_audio_video) et un [guide d'utilisation](https://developer.mozilla.org/fr/docs/Web/HTML/Utilisation_d'audio_et_video_en_HTML5) complet sont disponibles sur MDN
