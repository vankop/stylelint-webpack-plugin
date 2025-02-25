<div align="center">
  <a href="https://github.com/stylelint/stylelint"><img width="200" height="200" src="https://cdn.worldvectorlogo.com/logos/stylelint.svg"></a>
  <a href="https://github.com/webpack/webpack"><img width="200" height="200" src="https://webpack.js.org/assets/icon-square-big.svg"></a>
</div>

[![npm][npm]][npm-url]
[![node][node]][node-url]
[![deps][deps]][deps-url]
[![tests][tests]][tests-url]
[![coverage][cover]][cover-url]
[![chat][chat]][chat-url]
[![size][size]][size-url]

# stylelint-webpack-plugin

> A Stylelint plugin for webpack

## Install

```bash
npm install stylelint-webpack-plugin --save-dev
```

**Note**: You also need to install `stylelint` from npm, if you haven't already:

```bash
npm install stylelint --save-dev
```

## Usage

In your webpack configuration:

```js
const StylelintPlugin = require('stylelint-webpack-plugin');

module.exports = {
  // ...
  plugins: [new StylelintPlugin(options)],
  // ...
};
```

## Options

See stylelint's [options](http://stylelint.io/user-guide/node-api/#options) for
the complete list of options available. These options are passed through to the
`stylelint` directly.

### `configFile`

- Type: `String`
- Default: `undefined`

Specify the config file location to be used by `stylelint`.

_Note: By default this is [handled by `stylelint`](http://stylelint.io/user-guide/configuration/)._

### `context`

- Type: `String`
- Default: `compiler.context`

A string indicating the root of your style files.

### `files`

- Type: `String|Array[String]`
- Default: `'**/*.s?(a|c)ss'`

Specify the glob pattern for finding files. Must be relative to `options.context`.

### `formatter`

- Type: `Function`
- Default: `require('stylelint').formatters.string`

Specify a custom formatter to format errors printed to the console.

### `lintDirtyModulesOnly`

- Type: `Boolean`
- Default: `false`

Lint only changed files, skip lint on start.

### `stylelintPath`

- Type: `String`
- Default: `stylelint`

Path to `stylelint` instance that will be used for linting.

### `syntax`

- Type: `String`
- Default: `undefined`

See the `styelint` [user guide](https://stylelint.io/user-guide/node-api/#syntax) for more info.
e.g. use `'scss'` to lint .scss files.

### Errors and Warning

**By default the plugin will auto adjust error reporting depending on stylelint errors/warnings counts.**
You can still force this behavior by using `emitError` **or** `emitWarning` options:

#### `emitError`

- Type: `Boolean`
- Default: `false`

Will always return errors, if this option is set to `true`.

#### `emitWarning`

- Type: `Boolean`
- Default: `false`

Will always return warnings, if option is set to `true`.

#### `failOnError`

- Type: `Boolean`
- Default: `false`

Will cause the module build to fail if there are any errors, if option is set to `true`.

#### `failOnWarning`

- Type: `Boolean`
- Default: `false`

Will cause the module build to fail if there are any warnings, if option is set to `true`.

#### `quiet`

- Type: `Boolean`
- Default: `false`

Will process and report errors only and ignore warnings, if this option is set to `true`.

## Acknowledgement

This project was inspired by, and is a heavily modified version of
`sasslint-webpack-plugin`.

Thanks to Javier ([@vieron](https://github.com/vieron)) for authoring this
plugin.

## Changelog

[Changelog](CHANGELOG.md)

## License

[MIT](./LICENSE)

[npm]: https://img.shields.io/npm/v/stylelint-webpack-plugin.svg
[npm-url]: https://npmjs.com/package/stylelint-webpack-plugin
[node]: https://img.shields.io/node/v/stylelint-webpack-plugin.svg
[node-url]: https://nodejs.org
[deps]: https://david-dm.org/webpack-contrib/stylelint-webpack-plugin.svg
[deps-url]: https://david-dm.org/webpack-contrib/stylelint-webpack-plugin
[tests]: https://dev.azure.com/webpack-contrib/stylelint-webpack-plugin/_apis/build/status/webpack-contrib.stylelint-webpack-plugin?branchName=master
[tests-url]: https://dev.azure.com/webpack-contrib/stylelint-webpack-plugin/_build/latest?definitionId=4&branchName=master
[cover]: https://codecov.io/gh/webpack-contrib/stylelint-webpack-plugin/branch/master/graph/badge.svg
[cover-url]: https://codecov.io/gh/webpack-contrib/stylelint-webpack-plugin
[chat]: https://badges.gitter.im/webpack/webpack.svg
[chat-url]: https://gitter.im/webpack/webpack
[size]: https://packagephobia.now.sh/badge?p=stylelint-webpack-plugin
[size-url]: https://packagephobia.now.sh/result?p=stylelint-webpack-plugin
