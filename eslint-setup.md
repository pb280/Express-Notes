### Installing ESLint Extention in VSCode

<br>

Install ESLint extension from VSCode marketplace

<br>

### Installing dependencies for code formatting in NodeJS Projects

<br>

`npm install eslint prettier eslint-config-prettier eslint-plugin-prettier eslint-config-airbnb eslint-plugin-node eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react`

Saving these as '--save dev' flag.

<br>

### Make `.eslintrc.json` config file for ESLint

<br>

```
{
  "extends": ["airbnb", "prettier", "plugin:node/recommended"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error",
    "spaced-comment": "off",
    "no-console": "warn",
    "consistent-return": "off",
    "func-names": "off",
    "object-shorthand": "off",
    "no-process-exit": "off",
    "no-param-reassign": "off",
    "no-return-await": "off",
    "no-underscore-dangle": "off",
    "class-methods-use-this": "off",
    "prefer-destructuring": ["error", { "object": true, "array": false }],
    "no-unused-vars": ["error", { "argsIgnorePattern": "req|res|next|val" }]
  }
}
```

<br>

### Make `.prettierrc` config file for Prettier

<br>

```
{
  "singleQuote": true
}
```
