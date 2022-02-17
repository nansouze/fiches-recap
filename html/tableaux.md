# Les Tableaux

<p align="center">
  <img src='img/Tableur.png'  width='50%'>
</p>

## 3 Parties

D'un point de vue sémantique, il est recommandé de séparer un tableau en plusieurs 3 parties plus globales.

- `<thead>` Regroupe les éléments d'entête du tableau
- `<tfoot>` Regroupe les éléments de pieds du tableau
- `<tbody>` Défini le corps du tableau

### ⚠️ WARNING

> particularité pour `<tfoot>`, il peut se placer juste avant ou juste après `<tbody>`

<table>
  <thead>
    <tr>
      <th>Équipe</th>
      <th>Classement</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <th>Team Liquid</th>
      <th>WR 72%</th>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Team Liquid</td>
      <td>1421</td>
    </tr>
    <tr>
      <td>OG</td>
      <td>1402</td>
    </tr>
    <tr>
      <td>Evil Geniuses</td>
      <td>1311</td>
    </tr>
    <tr>
      <td>Team Faceless</td>
      <td>1278</td>
    </tr>
  </tbody>
</table>

`HTML`

```html
<table>
  <thead>
    <tr>
      <th>Équipe</th>
      <th>Classement</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <th>Team Liquid</th>
      <th>WR 72%</th>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Team Liquid</td>
      <td>1421</td>
    </tr>
    <tr>
      <td>OG</td>
      <td>1402</td>
    </tr>
    <tr>
      <td>Evil Geniuses</td>
      <td>1311</td>
    </tr>
    <tr>
      <td>Team Faceless</td>
      <td>1278</td>
    </tr>
  </tbody>
</table>
```

`CSS`

```css

table {
  border-collapse: collapse;
}

td, th {
  border: 1px solid black;
}

```

## Syntaxe

- `<table>` défini un tableau
- `<tr>` défini une ligne de tableau
- `<td>` défini une cellule de contenu
- `<th>` défini une cellule d'entête

<table>
  <thead>
    <tr>
      <th>Classique</th>
      <th>Heavy Metal</th>
      <th>Hip/hop</th>
      <th>Reggae</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beethoven</td>
      <td>AC/DC</td>
      <td>EPMD</td>
      <td>Bob Marley</td>
    </tr>
    <tr>
      <td>Mozart</td>
      <td>Iron Maiden</td>
      <td>The Notorious B.I.G.</td>
      <td>Peter Tosh</td>
    </tr>
    <tr>
      <td>Chopin</td>
      <td>Black Sabbath</td>
      <td>Nas</td>
      <td>Alpha bondy</td>
    </tr>
  </tbody>
</table>

`HTML`

```html
<table>
  <thead>
    <tr>
      <th>Classique</th>
      <th>Heavy Metal</th>
      <th>Hip/hop</th>
      <th>Reggae</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beethoven</td>
      <td>AC/DC</td>
      <td>EPMD</td>
      <td>Bob Marley</td>
    </tr>
    <tr>
      <td>Mozart</td>
      <td>Iron Maiden</td>
      <td>The Notorious B.I.G.</td>
      <td>Peter Tosh</td>
    </tr>
    <tr>
      <td>Chopin</td>
      <td>Black Sabbath</td>
      <td>Nas</td>
      <td>Alpha bondy</td>
    </tr>
  </tbody>
</table>
```

`CSS`

```css

table {
  border-collapse: collapse;
}

td, th {
  border: 1px solid black;
}

```

## Fusion 

Il est possible de rassembler le contenu de certaines lignes ou cellules en les fusionnant

- `rowspan` fusionne des lignes entre elles
- `colspan` fusionne des cellules entre elles

<table>
  <thead>
    <tr>
      <th colspan="3">AC/DC dans les charts Australiens</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="4">1976</th>
      <td>19</td>
      <td>T.N.T.</td>
    </tr>
    <tr>
      <td>9</td>
      <td>It's a Long Way to the Top</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Jailbreak</td>
    </tr>
    <tr>
      <td>29</td>
      <td>Dirty Deeds Done Dirt Cheap</td>
    </tr>
  </tbody>
</table>

`HTML`

```html
<table>
  <thead>
    <tr>
      <th colspan="3">AC/DC dans les charts Australiens</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="4">1976</th>
      <td>19</td>
      <td>T.N.T.</td>
    </tr>
    <tr>
      <td>9</td>
      <td>It's a Long Way to the Top</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Jailbreak</td>
    </tr>
    <tr>
      <td>29</td>
      <td>Dirty Deeds Done Dirt Cheap</td>
    </tr>
  </tbody>
</table>
```

`CSS`

```css
table {
  border-collapse: collapse;
}

td, th {
  border: 1px solid black;
}
```

