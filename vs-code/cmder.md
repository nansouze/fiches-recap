# Cmder VS Code [Documentation](https://code.visualstudio.com/docs/editor/integrated-terminal#_terminal-profiles)

## Répertoire Installation

`C:\Program Files\cmder`

## Fichier JSON VS Code

Il faut ouvrir le fichier `settings.json` `CTRL` + `SHIFT` + `P`.

```json

"terminal.integrated.profiles.windows": {
        "Cmder": {
          "path": "C:\\WINDOWS\\System32\\cmd.exe",
          "args": ["/K", "C:\\Program Files\\cmder\\vendor\\git-for-windows\\bin\\bash.exe"]
        }
},
"terminal.integrated.defaultProfile.windows": "Cmder",

```
