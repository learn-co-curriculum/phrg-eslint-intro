# ESLint

Just like Ruby has `rubocop`, Javascript has libraries that lint code to standardize its composition. Nitro uses a tool call `ESLint` for linting.

[Read about its basic usage and configuration here before continuing on in this README](https://eslint.org/docs/user-guide/getting-started).

ESLint uses 0, 1, and 2 to signify `off`, `warn`, and `error` for its `rules`, the equivalent of `cops` in Ruby's `rubocop`. Besides `rules`, there are [many other configurations](https://eslint.org/docs/user-guide/configuring) that may go into an `.eslintrc.json` file.

We do not need to dig into the meaning of each of these key/value pairs, but it is good to know where to look them up if we encounter a Javascript linting issue while writing code in Nitro.

Here is an example `.eslintrc.json` in Nitro. Notice that it extends a lot of recommended ESLint, React and Flow settings. It also granularly sets many React specific settings.

```json
{
  "plugins": [
    "flowtype",
    "jsx-control-statements",
    "react"
  ],
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:jsx-control-statements/recommended",
    "plugin:flowtype/recommended"
  ],
  "parser": "babel-eslint",
  "parserOptions": {
    "ecmaVersion": 6,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    }
  },
  "env": {
    "browser": true,
    "node": true,
    "mocha": true
  },
  "globals": {
    "NitroPubsub": true
  },
  "rules": {
    "no-console": 1,
    "react/prop-types": 1,
    "react/forbid-prop-types": 2,
    "react/jsx-boolean-value": 1,
    "react/jsx-closing-bracket-location": 1,
    "react/jsx-curly-spacing": 2,
    "react/jsx-handler-names": 2,
    "react/jsx-indent-props": 1,
    "react/jsx-key": 2,
    "react/jsx-max-props-per-line": 1,
    "react/jsx-no-bind": 1,
    "react/jsx-no-literals": 1,
    "react/jsx-pascal-case": 2,
    "react/jsx-sort-props": 1,
    "react/jsx-wrap-multilines": 1,
    "react/no-danger": 1,
    "react/no-did-mount-set-state": 2,
    "react/no-did-update-set-state": 2,
    "react/no-multi-comp": 1,
    "react/no-set-state": 1,
    "react/prefer-es6-class": 2,
    "react/self-closing-comp": 1,
    "react/sort-comp": 1
  },
  "settings": {
    "react": {
      "version": "detect"
    }
  }
}
```
