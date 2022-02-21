# Bugs

## En Cas de suppression de votre fichier .git (cloné depuis GitHub)

```sh

git init
git remote add origin ssh@le/lien/vers/ton/repo.git
git add .
git commit -m "on envoiiiie"
git push origin --force master

```

## En cas de dépôt local corrompu

Si vous avez des messages du type:

```sh

error: object file .git/objects/31/65329bb680e30595f242b7c4d8406ca63eeab0 is empty.

```

```sh

fatal: loose object 3165329bb680e30595f242b7c4d8406ca63eeab0 (stored in .git/objects/31/65329bb680e30595f242b7c4d8406ca63eeab0) is corrupt.

```

C'est que votre dépôt local est corrompu. Voici la manoeuvre pour réparer:

```sh

find .git/objects/ -type f -empty | xargs rm
git fetch -p
git fsck --full

```

## En cas de bétises

Il suffit juste de connaître les bonnes commandes 😉.

Voici donc 2 ressources qui expliquent bien ces commandes, et dans quel cas les utiliser.

- [Ohshitgit](https://ohshitgit.com/fr)
- [Dangitgit](https://dangitgit.com/fr)
