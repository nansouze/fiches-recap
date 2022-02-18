# Les Formulaires [MDN](https://developer.mozilla.org/fr/docs/Learn/Forms)

## `<form>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Form)

Tous les formulaires HTML débutent par un élément `<form>` comme celui-ci :

`HTML`

```html
<form action="traitement.php" method="post">

</form>
```

2 attributs sont nécessaires :

| Attribut  | Définition                                                                                             |
| :-------- | :----------------------------------------------------------------------------------------------------- | 
| `action`  | l'emplacement (une URL) où doivent être envoyées les données collectées par le formulaire              |
| `method`  | la méthode HTTP utilisée pour envoyer les données (cela peut être [GET](https://developer.mozilla.org/fr/docs/Learn/Forms/Sending_and_retrieving_form_data#la_m%C3%A9thode_get) ou [POST](https://developer.mozilla.org/fr/docs/Learn/Forms/Sending_and_retrieving_form_data#la_m%C3%A9thode_post))           |


## `<input>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Input)

### ⚠️ WARNING

> La balise `<input>` est un élément vide, ce qui signifie qu'il n'a pas besoin de balise fermante.

`HTML`

```html
<input type="text" name="prenom" value="jean-françois">
```

| Attribut      | Définition                                                                                              |
| :------------ | :------------------------------------------------------------------------------------------------------ | 
| `type`        | type de l'input: `text` `email` `password` `number` ... [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Input#les_diff%C3%A9rents_types_de_champs_input)                  |
| `name`        | le nom du champ qui sera rattaché à la donnée envoyée via le formulaire                                 |
| `value`       | la valeur du champ                                                                                      |
| `size`        | taille spécifique                                                                                       |
| `maxlength`   | longueur max                                                                                            |
| `placeholder` | description du champ qui s'éfface lors de la saisie                                                     |
| `autofocus`   | un attribut booléen qui passe le focus sur le champ lorsque le formulaire est affiché                   |
| `required`    | un attribut booléen qui indique que le champ doit être renseigné avant de pouvoir envoyer le formulaire |

## `<label>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Label)

Les labels permettent d'ajouter un titre contextuel à un champ.

`HTML`

```html
<label>Nom :</label>
<input type="text" name="user_name">
```

### ⚠️ WARNING

> Il est possible d'associer le label et le champ qu'il représente avec l'attribut `for` sur le label qui devra faire écho à l'attribut `id` placé sur l'élément en rapport. Un clic sur le label lancera un focus du champ associé.

> Il est recommandé d'englober `label` & `<input>` dans un `div`.

`HTML`

```html
<div>
    <label for="name">Nom :</label>
    <input type="text" id="name" name="user_name">
</div>
```

## `<textarea>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Textarea)

Il représente un contrôle qui permet d'éditer du texte sur plusieurs lignes.

### ⚠️ WARNING

> Il est possible de mettre un texte par défaut.

`HTML`

```html
<div>
    <label for="msg">Message :</label>
    <textarea id="msg" name="user_message" rows="5" cols="33">Ceci est un texte par défaut</textarea>
</div>
```

| Attribut  | Définition                                                                                |
| :-------- | :---------------------------------------------------------------------------------------- | 
| `rows`    | le nombre de lignes de texte visibles pour le contrôle                                    |
| `cols`    | la largeur visible du contrôle de saisie, exprimée en largeur moyenne de caractères. La valeur utilisée doit être un entier positif. La valeur par défaut de cet attribut est 20                                                                           |

## Les Eléments Options

### Checkbox [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Input/checkbox)

### ⚠️ WARNING

> Il est possible d'ajouter un attribut `checked` afin de sélectionner une option particulière par défaut.

`HTML`

```html
<p>Cochez vos qualités:</p>

<div>
  <input type="checkbox" id="social" name="social" checked>
  <label for="social">Social</label>
</div>

<div>
  <input type="checkbox" id="aimable" name="aimable">
  <label for="aimable">Aimable</label>
</div>
```

### Radio [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Input/radio)

### ⚠️ WARNING

> Il est possible d'ajouter un attribut `checked` afin de sélectionner une option particulière par défaut.

> L'attribut `name` est le point commun entre toutes les valeurs associées.

`HTML`

```html
<p>Situation Personnelle:</p>

<div>
  <input type="radio" id="celibataire" name="statut" value="celibataire" checked>
  <label for="celibataire">Célibataire</label>
</div>

<div>
  <input type="radio" id="marie" name="statut" value="marie">
  <label for="marie">Marié</label>
</div>

<div>
  <input type="radio" id="divorce" name="statut" value="divorce">
  <label for="divorce">Divorcé</label>
</div>

<div>
  <input type="radio" id="veuf" name="statut" value="veuf">
  <label for="veuf">Veuf</label>
</div>

```

### ⚠️ WARNING

> **Choisir entre radio & checkbox** : Une checkbox se suffit à elle même pour avoir un intérêt, elle peut être cochée ou non. Les radios n'ont un intérêt que lorsqu'il y a au moins 2 possibilités.

- **checkbox** `J'ai lu et j'accepte les conditions générales ...`
- **radio** `Madame` ou `Monsieur`

## Liste de Sélection [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/select)

### Choix unique
Une liste de sélection est l'association de l'élément de liste `<select>` et de plusieurs éléments `<option>` qui représentent les choix possibles.

`<select>` prendra l'attribut `name` et les différentes `<option>` la valeur associée grâce à `value`.

Il est possible d'ajouter un attribut `selected` ou `selected="selected"` afin de sélectionner une option particulière par défaut. Sans cet attribut, le premier `<option>`de la liste est sélectionné par défaut.

`HTML`

```html
<label for="film-like">Quel film avez-vous préférez?:</label>

<select name="films" id="film-like">
    <option value="">-- Veuillez choisir une option --</option>
    <option value="starwars4">Star Wars IV</option>
    <option value="starwars5" selected>Star Wars V</option>
    <option value="starwars6">Star Wars VI</option>
</select>
```


### Choix multiples

Avec un attribut `multiple` sur le `<select>` il est possible de définir une liste à choix multiples.

En utilisant la touche `cmd` sur Mac ou `ctrl` sur Linux ou Windows il est possible de sélectionner plusieurs options.

`HTML`

```html
<label for="film-like">Quel film avez-vous préférez?:</label>

<select name="films" id="film-like" multiple>
    <option value="">-- Veuillez choisir une option --</option>
    <option value="starwars4">Star Wars IV</option>
    <option value="starwars5">Star Wars V</option>
    <option value="starwars6">Star Wars VI</option>
</select>
```

### ⚠️ WARNING

> Avec la balise `<optgroup>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Optgroup), il est possible de créer un groupe d'options parmi lesquelles on peut choisir dans un élément `<select>`.

`HTML`

```html
<label for="film-like">Quel film avez-vous préférez?:</label>

<select name="films" id="film-like">
    <optgroup label="StarWars">
        <option value="starwars4">Star Wars IV</option>
        <option value="starwars5">Star Wars V</option>
        <option value="starwars6">Star Wars VI</option>
    </optgroup>
    <optgroup label="Rocky">
        <option value="rocky1">Rocky I</option>
        <option value="rocky2">Rocky II</option>
        <option value="rocky3">Rocky III</option>
    </optgroup>
</select>
```

> Avec la balise `<datalist>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/datalist), il est possible de contenir un ensemble d'éléments `<option>` qui représentent les valeurs possibles pour d'autres contrôles.

`HTML`

```html
<label for="ice-cream-choice">Choose a flavor:</label>

<input list="ice-cream-flavors" id="ice-cream-choice" name="ice-cream-choice" />

<datalist id="ice-cream-flavors">
    <option value="Chocolate">
    <option value="Coconut">
    <option value="Mint">
    <option value="Strawberry">
    <option value="Vanilla">
</datalist>
```

## Soumettre un Formulaire [MDN](https://developer.mozilla.org/fr/docs/Learn/Forms/Sending_and_retrieving_form_data)

Afin d'envoyer les informations saisies, il faut un déclencheur.

Il peut être de 2 types:

`HTML`

```html
<input type="submit" value="Envoyer">
```

```html
<button>Envoyer</button>
```
