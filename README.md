# Getting Started with Create React App

## `customize-cra`

#### 1) How to install

```bash
npm i customize-cra react-app-rewired -D
```

#### 2) Create a `config-overrides.js` file in the root directory

```javascript
/* config-overrides.js */

module.exports = function override(config, env) {
    //do stuff with the webpack config...
    return config;
};
```

#### 3) 'Flip' the existing calls to `react-scripts` in `npm` scripts for start, build and test

```diff
  /* package.json */

  "scripts": {
-   "start": "react-scripts start",
+   "start": "react-app-rewired start",
-   "build": "react-scripts build",
+   "build": "react-app-rewired build",
-   "test": "react-scripts test",
+   "test": "react-app-rewired test",
    "eject": "react-scripts eject"
}
```

## `babel-plugin-module-resolver`

```bash
npm i --save-dev babel-plugin-module-resolver
```

#### 1) Specify the plugin in your .babelrc with the custom root or alias. Here's an example:

```json
{
    "plugins": [
        [
            "module-resolver",
            {
                "alias": {
                    "~": "./src"
                }
            }
        ]
    ]
}
```

### 2) Editors autocompletion

-   Atom: Uses [atom-autocomplete-modules][atom-autocomplete-modules] and enable the `babel-plugin-module-resolver` option.
-   VS Code: Configure the [path mapping](https://www.typescriptlang.org/docs/handbook/module-resolution.html#path-mapping) in `jsconfig.json` (`tsconfig.json` for TypeScript), e.g.:

```js
{
    "compilerOptions": {
      "baseUrl": ".",
      "paths": {
        "~/*": ["src/*"]
      }
    }
}
```

## `customize-cra with webpack`

```javascript
const { override, useBabelRc } = require('customize-cra');

module.exports = override(
    // eslint-disable-next-line react-hooks/rules-of-hooks
    useBabelRc(),
);
```

## `prettierrc`

### 1) Create `.prettierrc` in the root

```json
{
    "arrowParens": "always",
    "bracketSameLine": false,
    "bracketSpacing": true,
    "embeddedLanguageFormatting": "auto",
    "htmlWhitespaceSensitivity": "css",
    "insertPragma": false,
    "jsxSingleQuote": false,
    "printWidth": 120,
    "proseWrap": "preserve",
    "quoteProps": "as-needed",
    "requirePragma": false,
    "semi": true,
    "singleQuote": true,
    "tabWidth": 4,
    "trailingComma": "all",
    "useTabs": false,
    "vueIndentScriptAndStyle": false
}
```

### 2) Create `.vscode/settings.json`

```json
{
    "editor.formatOnSave": true,
    "editor.defaultFormatter": "esbenp.prettier-vscode",
    "emmet.triggerExpansionOnTab": true,
    "emmet.includeLanguages": {
        "javascript": "javascriptreact"
    }
}
```

### `sass`

```bash
npm i -D sass
```
