<h2 align="center"> Learn NodeJS</h2>


## Table of Contents

- [Update Node](#update-node)
  - [Windows](#windows)
- [Install and Update Yarn](#install-and-update-yarn)
  - [Windows](#on-windows)
- [VS Code Editor Setup](#vs-code-editor-setup)
  - [Extensions](#extensions)
  - [Settings](#settings)
  - [Set Line Breaks](#set-line-breaks)
- [Linting Setup](#linting-setup)
  - [Install Dev Dependencies](#install-dev-dependencies)
  - [Setup Linting Configuration file](#setup-linting-configuration-file)
  
## Update Node

Please follow the below instructions to update node in your machine:

### Windows

1. Update npm
   ```sh
   npm install npm@latest -g
   ```
2. Clear npm cache
   ```sh
   npm cache clean -f
   ```
3. Install n
   ```sh
   npm install -g n
   ```
4. Update node to latest version
   ```sh
   n latest
   ```
   
## Install and Update yarn

Please follow the below instructions to install or update yarn in your machine.

### On Windows

1. Install yarn
   ```sh
   npm install -g yarn
   ```
2. Update yarn
   ```sh
   yarn set version latest
   ```
## VS Code Editor Setup

In order to follow along the tutorial series, I recommend you to use Visual Studio Code Editor and install & apply the below extensions and settings.

### Extensions

Install the below extensions:

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Path Autocomplete](https://marketplace.visualstudio.com/items?itemName=ionutvmi.path-autocomplete)

### Settings

Go to your Visual Stuido Code `settings.json` file and add the below settings there:

```json
// config related to code formatting
"editor.defaultFormatter": "esbenp.prettier-vscode",
"editor.formatOnSave": true,
"[javascript]": {
  "editor.formatOnSave": false,
  "editor.defaultFormatter": null
},
"editor.codeActionsOnSave": {
  "source.fixAll.eslint": true,
  "source.organizeImports": true
},
"eslint.alwaysShowStatus": true
```

### Set Line Breaks

Make sure in your VS Code Editor, "LF" is selected as line feed instead of CRLF (Carriage return and line feed). To do that, just click LF/CRLF in bottom right corner of editor, click it and change it to "LF". If you dont do that, you will get errors in my setup.

<img src="https://user-images.githubusercontent.com/26122249/186798301-83b1e4f7-8e31-4c67-86d7-48519dd49a0f.png" alt="Line Feed" width="700">

<!-- LINTING SETUP -->

## Linting Setup

In order to lint and format your code automatically according to popular airbnb style guide, I recommend you to follow the instructions as described in video. References are as below.

### Install Dev Dependencies

```sh
yarn add -D eslint prettier
npx install-peerdeps --dev eslint-config-airbnb-base
yarn add -D eslint-config-prettier eslint-plugin-prettier
```

### Setup Linting Configuration file

Create a `.eslintrc.json` file in the project root and enter the below contents:

```json
{
  "extends": ["prettier", "airbnb-base"],
  "parserOptions": {
    "ecmaVersion": 12
  },
  "env": {
    "commonjs": true,
    "node": true
  },
  "rules": {
    "no-console": 0,
    "indent": 0,
    "linebreak-style": 0,
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 100,
        "tabWidth": 4,
        "semi": true
      }
    ]
  },
  "plugins": ["prettier"]
}
```
