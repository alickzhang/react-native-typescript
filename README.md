# react-native-typescript

This boilerplate is built with [expo](https://expo.io/)

## Get started

Install expo globally and initialize the project,

```bash
npm install expo-cli --global
expo init react-native-typescript
```

then in 'Choose a template', select 'blank (TypeScript)'.

### tsconfig.json

The tsconfig.json under the root directory specifies the compiler options required to compile the project. You can refer the config [here](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

### Install packages

The packages we install here includes:

- [React Navigation](https://reactnavigation.org)
- [Axios](https://github.com/axios/axios)
- [Lodash](https://lodash.com/docs)
- [Moment](https://momentjs.com)
- [React Native Elements](https://react-native-elements.github.io/react-native-elements)

```bash
npm install --save @react-native-community/masked-view @react-navigation/bottom-tabs @react-navigation/drawer @react-navigation/native @react-navigation/stack axios lodash moment react-native-elements react-native-gesture-handler react-native-reanimated react-native-safe-area-context
```

### Eslint and Prettier

Install eslint and prettier

```bash
npm install --save-dev @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint eslint-config-prettier eslint-plugin-prettier eslint-plugin-react prettier
```

create a .eslintrc.json under the root directory

```json
{
  "parser": "@typescript-eslint/parser",
  "extends": [
    "react-app",
    "plugin:react/recommended",
    "plugin:prettier/recommended",
    "plugin:@typescript-eslint/eslint-recommended",
    "plugin:@typescript-eslint/recommended",
    "prettier/@typescript-eslint"
  ],
  "parserOptions": {
    "ecmaVersion": 2018,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "rules": {
    "@typescript-eslint/explicit-function-return-type": "off"
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
```

create a .prettierrc.json under the root directory

```json
{
  "arrowParens": "avoid",
  "endOfLine": "auto",
  "printWidth": 120,
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "all"
}
```

## Project structure

```
project
|-- .eslintrc.json
|-- .prettier.json
|-- .tsconfig.json
│-- assets
|-- src
|   |-- app.json
│   │-- index.tsx
│   │-- App.tsx
|   |-- components
│       │-- index.tsx
|       |-- Component1
|           |-- index.tsx
|           |-- Component1.tsx
│       │-- ...
│
|   |-- screens
|       |-- Screen1
|           |-- Screen1.tsx
|       |-- ...
|   |-- ...
```

### Edit app.json

Add entryPoint which points to src/index.tsx

```json
{
  "expo": {
    "entryPoint": "src/index.tsx"
    // ...
  }
}
```

### Edit package.json

```diff
- "start": "expo start",
- "android": "expo start --android",
- "ios": "expo start --ios",
- "web": "expo start --web",
+ "start": "expo start --config src/app.json",
+ "android": "expo start --android --config src/app.json",
+ "ios": "expo start --ios --config src/app.json",
+ "web": "expo start --web --config src/app.json",
```

### Edit src/index.tsx

```tsx
import 'react-native-gesture-handler';
import React from 'react';
import { registerRootComponent } from 'expo';
import App from './App';

export default registerRootComponent(App);
```
