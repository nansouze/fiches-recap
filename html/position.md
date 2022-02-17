# Position [MDN](https://developer.mozilla.org/fr/docs/Web/CSS/position)

| Position   | Définition                     |
| :--------- | :----------------------------- |
| `static`   | Comportement normal (par défaut). L'élément est alors positionné dans le flux avec sa position. Les propriétés `top`, `right`, `bottom`, `left` et `z-index` ne s'appliquent pas. |
| `relative` | L'élément est positionné dans le flux normal du document puis décalé, par rapport à lui-même, selon les valeurs fournies par `top`, `right`, `bottom`, `left`. Le décalage n'a pas d'impact sur la position des éléments. |
| `absolute` | L'élément est retiré du flux normal et aucun espace n'est créé pour l'élément sur la page. Il est ensuite positionné par rapport à son ancêtre le plus proche qui est positionné s'il y en a un ou par rapport au bloc englobant initial sinon. La position finale de l'élément est déterminée par les valeurs de `top`, `right`, `bottom`, `left`. |
| `fixed`    | e positionnement fixe est semblable au positionnement absolu sauf qu'ici, le bloc englobant correspond au viewport si aucun ancêtre de l'élément ne possède une propriété `transform`, `perspective` ou `filter` qui est différente de none. |
| `sticky`   | Le positionnement adhérent est un mélange de positionnement relatif et de positionnement fixe. L'élément est considéré comme positionné de façon relative, jusqu'à ce qu'un seuil soit franchi. À partir de ce seuil, l'élément est positionné de façon fixe. |
