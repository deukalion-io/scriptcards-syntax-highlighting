# ScriptCards syntax highlighting extension for VS Code

## Setup
1. Download the `vcix` VS Code extension package in `download` folder.
2. Install the extension in VS Code by going to the Extensions panel (Cmd or Ctrl+Shift+X) and clicking on the `...` icon then `Install from VSIX`.
3. In VS Code, open the Command Palette (Cmd or Ctrl+Shift+P) and type in `settings.json` to open `Preferences: Open Settings (JSON)`. 
4. Add everything between the opening/closing curly braces of the `download/settings-example.json` file in the repo to your `settings.json`. That file contains basic syntax styling rules.
5. Change the `ENTER_YOUR_THEME_NAME_HERE` from the rules you copied into `settings.json` to the exact name of your current theme. You can find out the name of your theme by opening the Command Palette and typing 'theme' for `Preferences: Color Theme`. 

To determine the scope of a token you want to set styling for, open the Command Palette, type 'developer' and select `Developer: Inspect Editor Tokens and Scopes`. (This command has no default shortcut key but it might be useful to set one.) Clicking on various tokens will display the current scopes the cursor is in and the 'foreground' scope currently coloring the text in the popup panel. 

To add a color for a scope, add a JSON object to the `textMateRules` array, e.g.:
```
  {
      "scope": "output.statement.scriptcards",
      "settings": {
          "foreground": "#BA68C8"
      }
  },
```
The settings in `settings-example.json` use the [Google Material Design Palette](https://material.io/resources/color/#!/?view.left=0&view.right=0&primary.color=BA68C8). 
