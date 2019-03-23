# Commands to start react native project:

  ```sh
  $ react-native init <app_name>
  $ cd <app_name>
  ```

<br/>

###  MobX:
  ```sh
  $ yarn add mobx mobx-react
  ```
  To use decorators:
  ```sh
  $ yarn add -D @babel/plugin-proposal-decorators
  ```
  Add to `babel.config.js`
  > `plugins: ["@babel/plugin-proposal-decorators", {legacy: true}]`

<br/>

### ESLint
  ```sh
  $ yarn add -D babel-eslint eslint eslint-plugin-react eslint-plugin-react-native
  ```
  Add `.eslintrc` file (see example in this repo) with settings to project root

  If you want to use airbnb config:
  ```sh
  $ yarn add -D eslint-plugin-import eslint-plugin-jsx-a11y
  $ yarn add -D eslint-config-airbnb
  ```

<br/>

### Flow
  ```sh
  $ yarn add -D flow-bin@<version_form_flow_config> eslint-plugin-flowtype
  ```

  If using VS Code to avoid flow errors: `Code -> Preferences -> Settings -> Workspace Settings`:

  >`"javascript.validate.enable": false`
  >`"flow.useNPMPackagedFlow": true,`
  > `"flow.pathToFlow": "${workspaceRoot}/node_modules/.bin/flow"`

  Add `esproposal.decorators=ignore` to section `[options]` in `.flowconfig`
  to avoid flow errors about decorators

  If using babel path aliases or module-resolver add:
  >`module.name_mapper='^/\(.*\)$' -> '<PROJECT_ROOT>/\1'`

  To avoid error when import from root using resolved paths '/'
  
  Or to start imports with `src/`:
  > `module.name_mapper='^src/\(.*\)$' -> '<PROJECT_ROOT>/src/\1'`

<br/>

### Babel
  To import file from project root:
  ```sh 
  $ yarn add -D babel-plugin-module-resolver
  ```
  Add to `babel.config.js` under `plugins` section:
  > `["module-resolver", { cwd: "babelrc", root: ["./"], alias: { src: "./src" } } ]`
  
  Issue for react native: `https://github.com/tleunen/babel-plugin-module-resolver/issues/29`

  And: `https://github.com/tleunen/babel-plugin-module-resolver/issues/184`


<br/>

### Other
  Add `.editorconfig` if need it (see example in this repo).

  To use git hooks:
  ```sh 
  $ yarn add -D husky
  ```

Add to `scripts` section in `package.json`:
> `"eslint": "node_modules/.bin/eslint src/**"`

> `"flow": "node_modules/.bin/flow"`


Add to the root of `package.json`:
> `"husky": {
    "hooks": {
      "pre-commit": "yarn run eslint && yarn run flow",
      "pre-push": "yarn run eslint && yarn run flow"
    }
  }`
