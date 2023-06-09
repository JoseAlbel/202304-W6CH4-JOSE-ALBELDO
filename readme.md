# Week 6 - Challenge 4

## Calculadora WebService

Crea una calculadora en Node en forma de web.

El programa debe recibir dos números por query params
(p.e. <http://localhost:8000/calculator?a=6&b=3>), y devolver el siguiente HTML:

Resultados:

6 + 3 = 9

6 - 3 = 3

6 \* 3 = 18

6 / 3 = 2

Si el usuario no ha proporcionado alguno de los números o éstos no son de tipo número, la aplicación debe devolver un HTML con un mensaje de error e interrumpir la ejecución del programa con un código de error.

La app debe abrirse en un puerto por defecto que esté configurado como variable de entorno, pero también se tiene que poder decir expresamente por línea de comandos en qué puerto queremos que se abra (p.e., `node . --port 4000`). Usar el paquete `commander`.

Si la request no va a /calculator, la app debe responder con un 404.

## Opción extra

Recoger los números en un formulario y recalcular los valores, utilizando SOLO vanila TS

# Backend Node: TS - Eslint -Jest

## Setup

- npm init
- git init
- .editorconfig
- .gitignore
- TS

  ```shell
  npm i -D typescript @types/node
  ```

tsconfig

```shell
npx tsc --init
```

ESModule Config: package.json

```json
  "type": "module"
```

- ESLint

```shell
npx eslint --init
npm i -D eslint-config-prettier
```

Eslint config

```json
{
  "env": {
    "browser": true,
    "es2021": true,
    "node": true,
    "jest": true
  },
  "extends": ["xo", "prettier"],
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaVersion": 12,
    "sourceType": "module"
  },
  "plugins": ["@typescript-eslint"],
  "rules": {}
}
```

Prettier config: package.json

```json
  "prettier": {
    "singleQuote": true
  }
```

- Jest

```shell
npm i -D jest ts-jest @types/jest jest-ts-webcompat-resolver
```

jest config

```js
/** @type {import('ts-jest').JestConfigWithTsJest} */
export default {
  preset: 'ts-jest',
  testEnvironment: 'node',
  testPathIgnorePatterns: ['dist'],
  resolver: 'jest-ts-webcompat-resolver',
  collectCoverageFrom: ['src/**/*.ts'],
  coveragePathIgnorePatterns: ['index.ts'],
};
```

```shell >>test<<

npm i cross-env
´´´
npm i dotenv

npm run server ( para el sevidor)<<<<<<
```

para salir de NODE

es process error negativo
