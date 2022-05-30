# ScriptCards syntax highlighting extension for VS Code

Provides syntax highlighting for the [ScriptCards](https://wiki.roll20.net/Script:ScriptCards#Conditional_Statement_.28--.3F.29) scripting language by [kjaegers](https://github.com/kjaegers/ScriptCards/tree/main/ScriptCards_API), available on Roll20 via the ScriptCards API.

Once installed, VS Code will recognize `.txt` and `.scard` extensions as ScriptCards files.

## Setup
1. Download the `vcix` VS Code extension package in `download` folder.
2. Install the extension in VS Code by going to the Extensions panel (Cmd or Ctrl+Shift+X) and clicking on the `...` icon then `Install from VSIX`.
3. In VS Code, open the Command Palette (Cmd or Ctrl+Shift+P) and type in `settings.json` to open `Preferences: Open Settings (JSON)`. 
4. Add everything between the opening/closing curly braces of the `download/settings-example.json` to your `settings.json`. That file contains basic syntax styling rules.
5. Change the `ENTER_YOUR_THEME_NAME_HERE` from the rules you copied into `settings.json` to the exact name of your current theme. You can find out the name of your theme by opening the Command Palette and typing 'theme' for `Preferences: Color Theme`. 

## Configuration
To determine the scope of a token you want to set styling for, open the Command Palette, type 'developer' and select `Developer: Inspect Editor Tokens and Scopes`. (This command has no default shortcut key but it might be useful to set one.) Clicking on various tokens will display scope information in the popup panel, including:
- the current hierarchy of scopes the cursor is in 
- the 'foreground' scope currently coloring the text. 

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

## Scopes

Scopes are created by regular expression captures. 
Note that `_comment` and `_string` scopes begin with an underscore. This is distinguish from built-in TextMate scope names. 

_This table is not complete._

### Identifiers
|Scope name|Capture|
| --- | ---|
|`identifier.scriptcards`|All of the below|
|`api.identifier.scriptcards`|`--@`|
|`audioeffect.identifier.scriptcards`|`--a`|
|`branchlabel.identifier.scriptcards`|`--:`|
|`branchto.identifier.scriptcards`|`--^`|
|`builtin.identifier.scriptcards`|`--~`|
|`case.identifier.scriptcards`|`--c` or `--C`|
|`_comment.identifier.scriptcards`|`--/`|
|`condition.identifier.scriptcards`|`--?`|
|`condition-end.identifier.scriptcards`|`--]`|
|`echo.identifier.scriptcards`|`--e`|
|`exit.identifier.scriptcards`|`--X`|
|`gmwhisper.identifier.scriptcards`|`--*`|
|`info.identifier.scriptcards`|`--i` or `--I`|
|`loadstorage.identifier.scriptcards`|`--l` or `--L`|
|`loop.identifier.scriptcards`|`--%`|
|`objectmod.identifier.scriptcards`|`--!`|
|`output.identifier.scriptcards`|`--+`|
|`parameter.identifier.scriptcards`|`--#`|
|`proccall.identifier.scriptcards`|`-->`|
|`procreturn.identifier.scriptcards`|`--<`|
|`repeating.identifier.scriptcards`|`--R`|
|`roll.identifier.scriptcards`|`--=`|
|`_string.identifier.scriptcards`|`--&`|
|`storestorage.identifier.scriptcards`|`--s` or `--S`|
|`visualeffect.identifier.scriptcards`|`--v`|

### Statements
|Scope name|Capture|
| --- | ---|
|`api.statement.scriptcards`|Lines starting with `--@`|
|`audioeffect.statement.scriptcards`|Lines starting with `--a`|
|`branchlabel.statement.scriptcards`|Lines starting with `--:`|
|`branchto.statement.scriptcards`|Lines starting with `--^` and within branch statements|
|`builtin.statement.scriptcards`|Lines starting with `--~`|
|`case.statement.scriptcards`|Lines starting with `--c` or `--C`|
|`_comment.statement.scriptcards`|Lines starting with `--/` and inline after `branchlabel`, `branchto`, and `proccall` statements|
|`condition.statement.scriptcards`|Lines starting with `--?`|
|`echo.statement.scriptcards`|Lines starting with `--e`|
|`exit.statement.scriptcards`|Lines starting with `--X`|
|`gmwhisper.statement.scriptcards`|Lines starting with `--*`|
|`info.statement.scriptcards`|Lines starting with `--i` or `--I`|
|`loadstorage.statement.scriptcards`|Lines starting with `--l` or `--L`|
|`loop.statement.scriptcards`|Lines starting with `--%`|
|`objectmod.statement.scriptcards`|Lines starting with `--!`|
|`output.statement.scriptcards`|Lines starting with `--+`|
|`parameter.statement.scriptcards`|Lines starting with `--#`|
|`proccall.statement.scriptcards`|Lines starting with `-->`|
|`procreturn.statement.scriptcards`|Lines starting with `--<`|
|`repeating.statement.scriptcards`|Lines starting with `--R`|
|`roll.statement.scriptcards`|Lines starting with `--=`|
|`_string.statement.scriptcards`|Lines starting with `--&`|
|`storestorage.statement.scriptcards`|Lines starting with `--s` or `--S`|
|`visualeffect.statement.scriptcards`|Lines starting with `--v`|

### Tags
|Scope name|Capture|
|---|---|
|`tag.scriptcards`|All of the below|
|`api.tag.scriptcards`|Between `--@` and `\|`|
|`audioeffect.tag.scriptcards`|Between `--a` and `\|` (if any)|
|`branchlabel.tag.scriptcards`|Between `--:` and `\||
|`branchto.tag.scriptcards`|Between `--^` and `\|`|
|`builtin.tag.scriptcards`|Between `--~` and `\|`|
|`case.tag.tag`|Between `--c` or `--C` and `\|`|
|`condition.tag.scriptcards`|Between `--?` and `\|`|
|`echo.tag.scriptcards`|Between `--e` and `\|`|
|`gmwhisper.tag.scriptcards`|Between `--*` and `\|` (if any)|
|`loadstorage.tag.scriptcards`|Between `--l` or `--L` and `\|`|
|`loop.tag.scriptcards`|Between `--%` and `\|`|
|`objectmod.tag.scriptcards`|Between `--!` and `\|`|
|`output.tag.scriptcards`|Between `--+` and `\|` (if any)|
|`parameter.tag.scriptcards`|Between `--#` and `\|`|
|`proccall.tag.scriptcards`|Between `--#` and `\|`|
|`roll.tag.scriptcards`|Between `--=` and `\|`|
|`_string.tag.scriptcards`|Between `--&` and `\|`|
|`storestorage.tag.scriptcards`|Between `--s` or `--S` and `\|`|
|`visualeffect.tag.scriptcards`|Between `--v` and `\|`|

### References