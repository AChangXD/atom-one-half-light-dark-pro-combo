# One Light Italic

**Project unmaintained**.

I recommend the [Yi Theme][yi-theme] for you. It is the only true port of
Atom's One theme I've known. Most all of the other Atom one light themes
use the `.tmTheme` color format or a direct json conversion of this format.
(`.tmTheme` stands for TextMate theme, some editors like Sublime and VSCode
have support for this legacy format.)

It looks like the [Yi Theme][yi-theme] stands out from all the other Atom themes
(not only the light ones) cause

- It's a true port from Atom's One theme based on the source code of Atom
- It includes both light and dark themes
- It covers not only the text syntax color, but also colors for the other part
  of the VSCode UI, like workbench.

It's a pity that Yi Theme doesn't include "Atom One" in its name and doesn't
appear in the search result of keyword like "atom one theme" in the marketplace.

For anyone like the italic syntax in this color theme, use following
*token color customization* settings.

<details>
<summary>editor.tokenColorCustomizations</summary>

```jsonc
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      { // from Atom One Dark
        "name": "js/ts italic",
        "scope":[
          // Why not attribute-name, .html, .pseudo-class.css
          "entity.other.attribute-name.js",
          "entity.other.attribute-name.ts",
          "entity.other.attribute-name.jsx",
          "entity.other.attribute-name.tsx",
          // "variable.parameter", // TODO: too generic
          "variable.language.super",
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      { // from ejeldes.one-dark-italic-theme
        "name": "js ts this",
        "scope": [
          "var.this",
          "variable.language.this.js",
          "variable.language.this.ts",
          "variable.language.this.jsx",
          "variable.language.this.tsx",
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      // {
      //   "name": "comment",
      //   "scope": "comment.line.double-slash,comment.block.documentation",
      //   "settings": {
      //     "fontStyle": "italic"
      //   }
      // },
      // },
      { // from laggardkernel.vscode-theme-onelight
        "name": "Italic",
        "scope": [
          "comment",
          "comment.block variable.parameter",
          "comment.block",
          "comment.block.documentation entity.name.type",
          "comment.block.documentation punctuation.definition",
          "comment.block.documentation variable",
          "comment.block.documentation",
          "constant.language",
          "entity.name.class",
          "entity.other.attribute-name",
          "keyword",
          "keyword.operator.expression",
          "keyword.operator.new",
          "keyword.other.documentation",
          "keyword.other.phpdoc",
          "markup.changed",
          "markup.deleted",
          "markup.inserted",
          "markup.italic",
          "markup.quote",
          "punctuation.definition.comment",
          "punctuation.definition.italic",
          "storage",
          "storage.type.class.jsdoc",
          "string.comment",
          "variable.language",
          //
          // "variable.parameter",
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      { // From laggardkernel.vscode-theme-onelight
        "name": "No Italic",
        "scope": [
          "entity.name.tag",
          "keyword.operator",
          "keyword.other.unit",
          "keyword.other.special-method",
          "support.type.property-name",
        ],
        "settings": {
          "fontStyle": "" // empty for normal
        }
      }
    ]
  }
```

</details>

Besides, here's also my custom terminal color definition. A modified version of
base16 "One Light" and "Onedark". Just put it here in case anyone wanna have
a try.

<details>
<summary>terminal color customization</summary>

```jsonc
  "terminal.integrated.drawBoldTextInBrightColors": false,
  // One Half Light modified, based on https://glitchbone.github.io/vscode-base16-term/
  "workbench.colorCustomizations": {
    "[Yi Light]": {
      "terminal.foreground":          "#383a42",
      "terminal.background":          "#fafafa",
      // "terminal.selectionForeground": "#383a42",
      "terminal.selectionBackground": "#bfceff",
      "terminalCursor.foreground":    "#cc00be",
      "terminal.border":              "#657b83",
      "terminal.ansiBlack":           "#383a42",
      "terminal.ansiRed":             "#e45649",
      "terminal.ansiGreen":           "#50a14f",
      "terminal.ansiYellow":          "#c18401",
      "terminal.ansiBlue":            "#2f5af3",
      "terminal.ansiMagenta":         "#a626a4",
      "terminal.ansiCyan":            "#00b7eb",
      "terminal.ansiWhite":           "#fafafa",
      "terminal.ansiBrightBlack":     "#797979",
      "terminal.ansiBrightRed":       "#e06c75",
      "terminal.ansiBrightGreen":     "#98c379",
      "terminal.ansiBrightYellow":    "#e5c07b",
      "terminal.ansiBrightBlue":      "#4b72ff",
      "terminal.ansiBrightMagenta":   "#c678dd",
      "terminal.ansiBrightCyan":      "#00b7eb",
      "terminal.ansiBrightWhite":     "#fafafa",
    },
    "[Yi Dark]": {
      "terminal.foreground":          "#dcdfe4",
      "terminal.background":          "#282c34",
      // "terminal.selectionForeground": "#dcdfe4",
      "terminal.selectionBackground": "#454D95",
      "terminalCursor.foreground":    "#cc00be",
      "terminal.border":              "#555555",
      "terminal.ansiBlack":           "#282c34",
      "terminal.ansiRed":             "#e06c75",
      "terminal.ansiGreen":           "#98c379",
      "terminal.ansiYellow":          "#e5c07b",
      "terminal.ansiBlue":            "#61afef",
      "terminal.ansiMagenta":         "#c678dd",
      "terminal.ansiCyan":            "#56b6c2",
      "terminal.ansiWhite":           "#dcdfe4",
      "terminal.ansiBrightBlack":     "#5d677a",
      "terminal.ansiBrightRed":       "#e06c75",
      "terminal.ansiBrightGreen":     "#98c379",
      "terminal.ansiBrightYellow":    "#e5c07b",
      "terminal.ansiBrightBlue":      "#61afef",
      "terminal.ansiBrightMagenta":   "#c678dd",
      "terminal.ansiBrightCyan":      "#56b6c2",
      "terminal.ansiBrightWhite":     "#dcdfe4",
    },
  },
```

</details>

---

Atom one light theme with italic support for VSCode.

[Github Repo](https://github.com/laggardkernel/vscode-theme-onelight)

Althought this them defines light ansi colors for terminal, it's designed to
be used by TUI apps but not the shell itself.

```json
"terminal.integrated.drawBoldTextInBrightColors": false,
```

## Ref

- [How to make your own VS Code theme!](https://www.youtube.com/watch?v=pGzssFNtWXw)
- [VSCode Color Theme Guide](https://code.visualstudio.com/api/extension-guides/color-theme)
- [VSCode Color Theme Reference](https://code.visualstudio.com/api/references/theme-color)
- [VSCode Publish Extensions Guide](https://code.visualstudio.com/api/working-with-extensions/publishing-extension)
- [One Light tmTheme](https://github.com/akamud/vscode-theme-onelight/blob/master/themes/OneLight.old.tmTheme)
- [One Half Light tmTheme](https://tmtheme-editor.herokuapp.com/#!/editor/theme/One%20Half%20Light)
- [GitHub's VS Code themes](https://marketplace.visualstudio.com/items?itemName=GitHub.github-vscode-theme)
- [atom one-light-syntax](https://github.com/atom/atom/tree/master/packages/one-light-syntax)

[yi-theme]: https://marketplace.visualstudio.com/items?itemName=wangweixuan.yithemes
