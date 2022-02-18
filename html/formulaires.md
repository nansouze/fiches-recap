# Les Formulaires [MDN](https://developer.mozilla.org/fr/docs/Learn/Forms)

## `<form>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Form)

Tous les formulaires HTML débutent par un élément `<form>` comme celui-ci :

`HTML`

```html
<form action="traitement.php" method="post">

</form>
```

2 attributs sont nécessaires :

| Attribut  | Définition                                                                                |
| :-------- | :---------------------------------------------------------------------------------------- | 
| `action`  | l'emplacement (une URL) où doivent être envoyées les données collectées par le formulaire |
| `method`  | la méthode HTTP utilisée pour envoyer les données (cela peut être « get » ou « post »)    |


## `<input>` [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Input)

### ⚠️ WARNING

> La balise `<input>` est un élément vide, ce qui signifie qu'il n'a pas besoin de balise fermante.

`HTML`

```html
<input type="text" name="prenom" value="jean-françois">
```

| Attribut      | Définition                                                                                |
| :------------ | :---------------------------------------------------------------------------------------- | 
| `type`        | type de l'input: `text` `email` `password` `number` ... [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Input#les_diff%C3%A9rents_types_de_champs_input)    |
| `name`        | le nom du champ qui sera rattaché à la donnée envoyée via le formulaire                   |
| `value`       | la valeur du champ                                                                        |
| `size`        | taille spécifique                                                                         |
| `maxlength`   | longueur max                                                                              |
| `placeholder` | description du champ qui s'éfface lors de la saisie                                                              |


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


