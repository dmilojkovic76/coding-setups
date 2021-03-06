# Podešavanja za Visual Studio Code

## Extensions
#### Workflow
* [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=coenraads.bracket-pair-colorizer)
  - A customizable extension for colorizing matching brackets
* [Auto Close Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-close-tag)
  - Automatically add HTML/XML close tag, same as Visual Studio IDE or Sublime Text
* [Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)
  - Auto rename paired HTML/XML tag
* [advanced-new-file](https://marketplace.visualstudio.com/items?itemName=patbenatar.advanced-new-file)
  - Create files anywhere in your workspace from the keyboard
#### Editing
* [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
  - Integrates ESLint JavaScript into VS Code.
* [Beautify](https://marketplace.visualstudio.com/items?itemName=hookyqr.beautify)
  - Beautify javascript, JSON, CSS, Sass, and HTML in Visual Studio Code.
* [Babel JavaScript](https://marketplace.visualstudio.com/items?itemName=mgmcdermott.vscode-language-babel)
  - JavaScript syntax highlighting for ES201x, React JSX, Flow and GraphQL. Only the syntax highlighting. The transpiling and configuration is not included.
#### Coding helpers
* [IntelliSense for CSS class names in HTML](https://marketplace.visualstudio.com/items?itemName=Zignd.html-css-class-completion)
  - CSS class name completion for the HTML class attribute based on the definitions found in your workspace.
* [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)
  - Visual Studio Code plugin that autocompletes filenames
* [Npm Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.npm-intellisense)
  - Visual Studio Code plugin that autocompletes npm modules in import statements
#### Additional tools
* [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
  - Launch a development local Server with live reload feature for static & dynamic pages
* [GitLens — Git supercharged](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
  - Visualize code authorship at a glance via Git blame annotations and code lens, seamlessly navigate and explore Git repositories, gain valuable insights via powerful comparison commands, and so much more
* [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)
  - Vue tooling for VS Code, powered by [vue-language-server](https://github.com/vuejs/vetur/tree/master/server).
* [Import Cost](https://marketplace.visualstudio.com/items?itemName=wix.vscode-import-cost)
  - This extension will display inline in the editor the size of the imported package.
* [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)
  - Live Scratchpad for JavaScript - a rapid prototyping playground in your editor, with access to your project’s files, inline reporting, code coverage and rich output formatting.
  
## Spisak ekstenzija (korisno za command line tj. terminal) i automatizaciju instalacije:
Dobija se pomoću:
  `code --list-extensions` .
Tu listu je mogće snimiti u fajl i u terminalu instalirti jednu po jednu pomoću:
  `code --install-extension ( | )`.
U **bash**-u na primer može:
```sh
cat file... | xargs -n1 code --install-extension
```

Sa [Visual Studio Code Docs](https://code.visualstudio.com/docs/editor/extension-gallery):

_Extensions are installed in a per user extensions folder. Depending on your platform, the location is in the following folder:
  **Windows** ```sh %USERPROFILE%\.vscode\extensions ```
  **macOS** ```sh ~/.vscode/extensions ```
  **Linux** ```sh ~/.vscode/extensions ```
You can change the location by launching VS Code with the `--extensions-dir <dir>` command line option._

**Lista:**
```
christian-kohler.npm-intellisense
christian-kohler.path-intellisense
CoenraadS.bracket-pair-colorizer
dbaeumer.vscode-eslint
eamodio.gitlens
formulahendry.auto-close-tag
formulahendry.auto-rename-tag
HookyQR.beautify
mgmcdermott.vscode-language-babel
octref.vetur
patbenatar.advanced-new-file
ritwickdey.LiveServer
robertohuertasm.vscode-icons
WallabyJs.quokka-vscode
wix.vscode-import-cost
Zignd.html-css-class-completion
```

## Moj _minimal_ user `settings.json` fajl:
```json
{
    "workbench.iconTheme": "vscode-icons",
    "files.autoSave": "onFocusChange",
    "team.showWelcomeMessage": false,
    "gitlens.advanced.messages": {
        "suppressShowKeyBindingsNotice": true
    },
    "git.autofetch": true,
    "workbench.startupEditor": "newUntitledFile",
    "editor.multiCursorModifier": "ctrlCmd",
    "editor.mouseWheelZoom": true,
    "editor.parameterHints.cycle": true,
    "editor.tabSize": 2,
    "editor.formatOnPaste": true
}
```

## Moj user `settings.json` fajl:
```json
{
    "editor.fontLigatures": true,
    "editor.formatOnPaste": false,
    "editor.mouseWheelZoom": true,
    "editor.multiCursorModifier": "ctrlCmd",
    "editor.parameterHints.cycle": true,
    "editor.snippetSuggestions": "top",
    "editor.tabSize": 2,
    "editor.fontSize": 16,
    "emmet.showAbbreviationSuggestions": false,
    "eslint.validate": [{
            "language": "vue",
            "autoFix": true
        },
        {
            "language": "html",
            "autoFix": true
        },
        {
            "language": "javascript",
            "autoFix": true
        }
    ],
    "explorer.openEditors.visible": 0,
    "files.autoSave": "onFocusChange",
    "gitlens.advanced.messages": {
        "suppressShowKeyBindingsNotice": true
    },
    "git.autofetch": true,
    "team.showWelcomeMessage": false,
    "window.zoomLevel": -1,
    "workbench.iconTheme": "vscode-icons",
    "workbench.startupEditor": "newUntitledFile"
}
```

## CJ's user `settings.json` fajl:
```json
{
  "editor.snippetSuggestions": "top",
  "editor.fontFamily": "Anonymous Pro",
  "workbench.iconTheme": "eq-material-theme-icons",
  "workbench.colorTheme": "Seti Monokai",
  "editor.multiCursorModifier": "ctrlCmd",
  "files.autoSave": "onFocusChange",
  "editor.tabSize": 2,
  "editor.fontSize": 21,
  "editor.formatOnPaste": false,
  "editor.minimap.enabled": false,
  "editor.fontLigatures": true,
  "editor.lineHeight": 0,
  "terminal.integrated.fontSize": 16,
  "explorer.openEditors.visible": 0,
  "window.zoomLevel": 1,
  "emmet.showAbbreviationSuggestions": false,
  "workbench.colorCustomizations": {
      "activityBarBadge.background": "#C6FF00",
      "list.activeSelectionForeground": "#C6FF00",
      "list.inactiveSelectionForeground": "#C6FF00",
      "list.highlightForeground": "#C6FF00",
      "scrollbarSlider.activeBackground": "#C6FF0050",
      "editorSuggestWidget.highlightForeground": "#C6FF00",
      "textLink.foreground": "#C6FF00",
      "progressBar.background": "#C6FF00",
      "pickerGroup.foreground": "#C6FF00",
      "tab.activeBorder": "#C6FF00",
      "notificationLink.foreground": "#C6FF00"
  },
  "eslint.validate": [
      {
          "language": "vue",
          "autoFix": true
      },
      {
          "language": "html",
          "autoFix": true
      },
      {
          "language": "javascript",
          "autoFix": true
      }
  ],
  "java.errors.incompleteClasspath.severity": "ignore",
  "workbench.startupEditor": "newUntitledFile"
}
```
