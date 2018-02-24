# Commands to start react native project:

  ```sh
  $ react-native init <app_name>
  $ cd <app_name>
  ```

###  MobX:
  ```sh
  $ yarn add mobx mobx-react
  $ yarn add --dev babel-plugin-transform-decorators-legacy
  ```
  Add `"plugins": ["transform-decorators-legacy"]` to `.babelrc`
  
### ESLint
  ```sh
  $ yarn add --dev babel-eslint eslint eslint-plugin-react eslint-plugin-react-native husky
  ```
  Add `.eslintrc` file with settings to project root

  If want to use airbnb config:
  ```sh
  $ yarn add -D eslint-plugin-import eslint-plugin-jsx-a11y
  $ yarn add -D eslint-config-airbnb
  ```
  
### Flow
  ```sh
  $ yarn add --dev flow-bin@<version_form_flow_config> eslint-plugin-flowtype
  ```
  Add `esproposal.decorators=ignore` to section `[options]` in `.flowconfig`
  to avoid flow error about decorators

  If using path aliases or module-resolver for babel add:
  `module.name_mapper='^/\(.*\)$' -> '<PROJECT_ROOT>/\1'`
  To avoid error when import from root using resolved paths '/'


### Babel
  To import file from project root:
  ```sh 
  $ yarn add --dev babel-plugin-module-resolver
  ```
  Add `["module-resolver", { "cwd": "babelrc", "root": ["./"] } ]` to `plugins` in `.babelrc`
  Issue for react native: `https://github.com/tleunen/babel-plugin-module-resolver/issues/29`
  And: `https://github.com/tleunen/babel-plugin-module-resolver/issues/184`


### Other
  Add `.editorconfig` if need it.
  
  Add navigator. For example:
  ```sh 
  $ yarn add react-navigation 
  ```
  If using VS Code to avoid flow errors: `Code -> Preferecies -> Settings -> Workspace Settings`:  
&nbsp;&nbsp;&nbsp;&nbsp;`"javascript.validate.enable": false`

Add to `scripts` section in `package.json`:
&nbsp;&nbsp;&nbsp;&nbsp;`"eslint": "eslint src/**"`,
&nbsp;&nbsp;&nbsp;&nbsp;`"flow": "node_modules/.bin/flow"`,
&nbsp;&nbsp;&nbsp;&nbsp;`"precommit": "npm run eslint && npm run flow"`
&nbsp;&nbsp;&nbsp;&nbsp;`"prepush": "npm run eslint && npm run flow"`,
