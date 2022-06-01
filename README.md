# version-bump

A script which will automatically increment your app package version in accordance with conventional commits

## Prerequisites
- [Git](https://git-scm.com/) installed and configured

## Installation

```js
# using npm
npm install version-bump

# using yarn
yarn add version-bump
```

## Usage

- Add the following script to your package.json<br/>
```js
  "scripts": {
      "bump-version": "npm explore version-bump -- npm run bump-version --name=<package_name>",
  } 
```
- then:

```js
# using npm
npm run bump-version

# using yarn
yarn bump-version
```

## Usage with commitlint and husky<br/>

- ### Install the following dependencies
```js
  "dependencies": {
    "@commitlint/cli": "^17.0.1",
    "@commitlint/config-conventional": "^17.0.0",
    "husky": "^4.3.8"
  }
```

- ### Add the following to your package.json<br/>
```js
  "config": {
    "commitizen": {
      "path": "cz-conventional-changelog"
    }
  },
  "husky": {
    "hooks": {
      "post-commit": "npm run bump-version",
    }
  },
  "commitlint": {
    "extends": [
      "@commitlint/config-conventional"
    ]
  }
```

## Commit message prefixes and associated version bumping<br/><br/>

- feature! / feat! / f! -
  - bump major version <br/><br/>

- feature / feat / f -
  - bump minor version <br/>

- fix -
  - bump patch version <br/>