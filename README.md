# Getting Started with Create React App

### `customize-cra`

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
