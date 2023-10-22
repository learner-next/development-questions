# ESLint

## This is a guide to setting up ESLint in your project and record usage questions when you use it.

## 1. Install ESLint

```bash
[npm|pnpm|bun] install eslint -D

or

yarn add eslint -D
```

## 2. Config ESLint(My React Config)
You can custom config rules or other configs by yourself through reading [ESLint]()

```Typescript
// .eslintrc.cjs
module.exports = {
  root: true,
  env: { browser: true, es2020: true, node: true },
  extends: [
    'eslint:recommended',
    'plugin:react/recommended',
    'plugin:@typescript-eslint/recommended',
    'plugin:react-hooks/recommended'
  ],
  ignorePatterns: ['dist', '.eslintrc.cjs'],
  parser: '@typescript-eslint/parser',
  plugins: ['react-refresh'],
  rules: {
    'react-refresh/only-export-components': [
      'warn',
      { allowConstantExport: true },
    ],
    "react/react-in-jsx-scope": "off",
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx", ".ts", ".tsx"] }],
    "react/no-unknown-property": [2, { "ignore": ["class"] }],
    "react-refresh/only-export-components": "off",
    "react/prop-types": "off",
  },
  settings: {
    react: { version: 'detect' },
  },
}
```

## Questions

### 1. eslint markdown parsing error: invalid character.eslint
ESLint parsing markdown error so you need to install `plugin:markdown/recommended` and add it to your `extends` config.

```Typescript
module.exports = {
  // other config
  extends: [
    // other extends
    'plugin:markdown/recommended',
  ],
}
```
