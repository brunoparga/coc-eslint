# coc-eslint

Eslint language server extension for [coc.nvim](https://github.com/neoclide/coc.nvim).

Forked from [vscode-eslint](https://github.com/Microsoft/vscode-eslint).

## Install

In your vim/neovim run the following command:

```sh
:CocInstall coc-eslint
```

## Features

- Lint `javascript` files using eslint.
- Provide `codeActions` for fixing lint issues.
- Provide eslint commands:
  - `eslint.createConfig` create eslint config file.
  - `eslint.executeAutofix` fix all fixable issues of current buffer.

## Configuration options

**Notice** these configuration settings allow you to configure the behaviour of the coc-eslint extension.

- `eslint.enable`: enable/disable ESLint. This is enabled by default.
- `eslint.quiet` - ignore warnings.
- `eslint.packageManager`: controls the package manager to be used to resolve the ESLint library. This has only an influence if the ESLint library is resolved globally. Valid values are `"npm"` or `"yarn"`.
- `eslint.options`: options to configure how ESLint is started using the [ESLint CLI Engine API](http://eslint.org/docs/developer-guide/nodejs-api#cliengine). Defaults to an empty option bag.
  An example to point to a custom `.eslintrc.json` file is:
  ```json
  {
    "eslint.options": {"configFile": "C:/mydirectory/.eslintrc.json"}
  }
  ```
- `eslint.run` - run the linter `onSave` or `onType`. The Default is `onType`.
- `eslint.autoFixOnSave` - enables auto fix on save.
- `eslint.nodePath` - use this setting if an installed ESLint package can't be detected. For example `/myGlobalNodePackages/node_modules`.
- `eslint.filetypes` - an array of language identifiers specifying the files to be validated. Something like `"eslint.validate": [ "javascript", "javascriptreact", "html" ]`. If the setting is missing, it defaults to `["javascript", "javascriptreact"]`.

## Auto-fixing

The extension supports automatic fixing of warnings to the extent that it is supported by eslint.
For warnings which support an auto-fix. You can apply the quick fix by either:

- Set `eslint.autoFixOnSave` to `true` and save your file (recommended).
- Trigger `<Plug>(coc-codeaction)` with mapped keys, and select a fix action in the input list.
- Run command `:CocCommand eslint.executeAutofix`.
- Trigger command `eslint.executeAutofix` from `:Denite coc-command`.

## License

MIT

