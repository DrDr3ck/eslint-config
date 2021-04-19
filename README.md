# Shared ESLint Config

This is the home of the shared E&P Software ESLint configs. The default config should be used for all React Typescript projects in E&P Software.

## Usage

The ESLint config and Prettier config must both be added to get the full shared configuration. The ESLint configuration includes the prettier plugin which will load the prettier config and report issues as errors.

### (1) Install the shared Prettier and ESLint configs

```bash
npm install --save-dev "https://github.com/emerson-eps/prettier-config.git#main" "https://github.com/emerson-eps/eslint-config.git#main"
```

If you have not already installed `prettier` and `eslint` install those as well:

```bash
npm install --save-dev prettier eslint
```

### (2) Configure Prettier

Add `@emerson-eps/prettier-config` to your `package.json`:

```json
{
  "prettier": "@emerson-eps/prettier-config"
}
```

For more advanced setups, including how to override settings, see the instructions in the [@emerson-eps/prettier-config](https://github.com/emerson-eps/prettier-config) repository.

### (3) Configure ESLint

Specify the package in the [`extends`](http://eslint.org/docs/user-guide/configuring#extending-configuration-files) section of your [ESLint configuration](http://eslint.org/docs/user-guide/configuring):

```js
{
  "extends": "@emerson-eps/eslint-config",
  "rules": {
    // Additional rules...
  }
}
```

## Running ESLint on your code

Add a lint script to your `package.json`, for example:

```json
{
  "scripts": {
    "lint": "eslint ."
  }
}
```

Code can then be linted with:

```
npm run lint
```

CI pipelines should be configured to fail on linting errors.

## Integration with Visual Studio Code

If not already installed, install the [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) and [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) extensions.

## Overriding the shared configs

Try not to override the shared configs unless you really need to. If you must override them please consider proposing the override as a change to the relevant repository first to avoid divergence of code styles in different projects.