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
| `type`  | type de l'input: `text` `email` `password` `number` |
| `name`  | la méthode HTTP utilisée pour envoyer les données (cela peut être « get » ou « post »)    |
| `value`  | la méthode HTTP utilisée pour envoyer les données (cela peut être « get » ou « post »)    |

