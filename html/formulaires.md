# Les Formulaires [MDN](https://developer.mozilla.org/fr/docs/Learn/Forms)

## `<form>`

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


## `<input>`

### ⚠️ WARNING

> La balise `<input>` est un élément vide, ce qui signifie qu'il n'a pas besoin de balise fermante.

`HTML`

```html
<input type="text" name="prenom" value="jean-françois">
```

| Attribut  | Définition                                                                                |
| :-------- | :---------------------------------------------------------------------------------------- | 
| `type`  | type de l'input: `text` `email` `password` `number` ... [MDN](https://developer.mozilla.org/fr/docs/Web/HTML/Element/Input#les_diff%C3%A9rents_types_de_champs_input)|
| `name`  | le nom du champ qui sera rattaché à la donnée envoyée via le formulaire                     |
| `value` | la valeur du champ                                                                          |


## `<label>`

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
