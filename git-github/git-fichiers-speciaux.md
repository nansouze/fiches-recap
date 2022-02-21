# Fichiers Spéciaux

| Nom       | Description                                                           |
| :-------- | :-------------------------------------------------------------------- |
| `.gitignore` | Permet de lister des fichiers qui doivent être ignorés lors du add |
| `.gitkeep`   | Fichier qui peut être placé à la racine d'un répertoire vide afin que git prenne ce dossier en compte même s'il ne contient pas de fichier |


```sh

######################
# GITIGNORE TEMPLATE #
######################

# Compiled Source #
###################
*.com
*.class
*.dll
*.exe
*.o
*.so

# Packages #
############
# it's better to unpack these files and commit the raw source
# git has its own built in compression methods
*.7z
*.dmg
*.gz
*.iso
*.jar
*.rar
*.tar
*.zip

# Node #
########
node_modules/

# Logs and Databases #
######################
*.log
*.sql
*.sqlite
.env

# OS Generated Files #
######################
.DS_Store
.DS_Store?
._*
.Spotlight-V100
.Trashes
ehthumbs.db
Thumbs.db

```
