# Opérateurs

## Opérateurs Arithmétiques

| Caractère    |  Opération     |
| :----------- | :------------- | 
| `+`          | Addition       |
| `-`          | Soustration    | 
| `*`          | Multiplication | 
| `/`          | Division       |
| `%`          | Modulo         |
| `**`         | Exponentielle  |

## Opérateurs Incrémentation & Décrémentation

```js

result++; // incrémentation = ajoute 1
result--; // décrémentation = retire 1
result += 2; // incrémentation = ajoute 2
result -= 2; // décrémentation = retire 2

```

## Opérateurs Comparaison

| Signe        |  Définition                       |
| :----------- | :-------------------------------- | 
| `==`         | Egal à la valeur                  |
| `===`        | Egal à la valeur et au type       | 
| `!=`         | Différent de la valeur            | 
| `!==`        | Différent de la valeur et du type |
| `>`          | Supérieur                         |
| `<`          | Inférieur                         |
| `>=`         | Supérieur ou égal                 |
| `<=`         | Inférieur ou égal                 |

## Opérateurs Logiques

`C1 && C2` (ET logique)
| C1      | C2       | Résultat          |
| :------ | :------- | :---------------- |
| `true`  | `true`   | `true`            |
| `true`  | `false`  | `false`           |
| `false` | `true`   | `false`           |
| `false` | `false`  | `false`           |

⚠️ **WARNING**
> Si la première valeur est [truthy](https://developer.mozilla.org/fr/docs/Glossary/Truthy), l'opérateur `&&` renvoie le deuxième opérande.

```js

true && "chien" // renvoie "chien"

[] && "chien" // renvoie "chien"

```

`C1 || C2` (OU logique)
| C1      | C2       | Résultat          |
| :------ | :------- | :---------------- |
| `true`  | `true`   | `true`            |
| `true`  | `false`  | `true`            |
| `false` | `true`   | `true`            |
| `false` | `false`  | `false`           |

⚠️ **WARNING**
> Si la première valeur est [falsy](https://developer.mozilla.org/fr/docs/Glossary/Falsy), l'opérateur `||` renvoie le deuxième opérande.

```js

false || "chien" // renvoie "chien"

null || "chien" // renvoie "chien"

```

`!C1` (NON logique)
| C1      | Résultat          |
| :------ | :---------------- |
| `true`  | `false`           |
| `false` | `true`            |

## Opérateur Conditionnel Ternaire

```js

// [CONDITION] ? [TRUE] : [FALSE]
let x = 2;

(x > 3) ? console.log("X est supérieur à trois") : console.log("X est inférieur à trois");

```

## Opérateur de Coalescence des Nuls (Nullish Coalescing Operator)

C'est un opérateur logique qui renvoie son opérande de droite lorsque son opérande de gauche vaut `null` ou `undefined` et qui renvoie son opérande de gauche sinon.

```js

const foo = null ?? 'default string';
console.log(foo); // expected output: "default string"

const baz = 0 ?? 42;
console.log(baz); // expected output: 0

```



