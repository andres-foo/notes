# Environment and useful tools

These are the choices I'm currently most comfortable with for Windows, but there're many other options.

## PowerShell

Check the current version by typing the following command on a PowerShell window:

```shell
$PSVersionTable
```

If you have a 5.x version, it will be suggested to download version 7.x.


## Laravel Herd

Laravel Herd provides:
- PHP
- Composer
- nodejs

Install _Laravel Herd_ and then verify the current installed versions with:

```shell
php -v
composer --version
node --version
```

If no _node_ version is showing, use the command:

```shell
# replace x.x.x with whatever version you have installed
nvm use x.x.x
```

You can use the `nvm` command to manage the versions for node.

## VSCode

### Theming
- **Theme** : GitHub Dark
- **Icons** : File Icons (Colourless)
- **Fonts** : Maple Mono, JetBrains Mono or Mononoki.

To add Italic to the theme, add the following to the user settings file:

```json
{
 "editor.fontFamily": "'Maple Mono'",
 "editor.tokenColorCustomizations": {
     "textMateRules": [
      {
        "scope": [
          "comment",
          "keyword.control",
          "keyword.operator.new",
          "keyword.operator.assignment",
          "keyword.operator.arithmetic",
          "storage.modifier",
          "storage.type",
          "support.class",
          "support.constant",
          "support.other",
          "entity.name.method",
          "entity.name.section",
          "entity.name.selector",
          "entity.name.type",
          "entity.other",
          "entity.other.attribute-name",
          "entity.other.inherited-class"
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": ["storage.type.function.arrow", "meta.paragraph.markdown"],
        "settings": {
          "fontStyle": ""
        }
      }
    ]
  }
}
```

Taken from [this link](https://gist.github.com/dev01d/2afddac00b14d61b753182f233951c30)

### Extensions

- GitHub Theme : For the color theme
- file-icons : For the file icons
- DotENV : dotenv files syntax support
- Duplicate action :  Allow to duplicate files from the context menu
- Laravel Blade Snippets : Snippets and syntax highlighting
- Laravel goto view : Quick jump to view
- PHP Intelephense : PHP code intelligence
- PHP Namespace Resolver: Import and expand namespaces
- Prettier: Code formatting for css and javascript
- Rainbow CSV :  Highlight CSV files
- Tailwind CSS IntelliSense : Intelligent Tailwind CSS tooling