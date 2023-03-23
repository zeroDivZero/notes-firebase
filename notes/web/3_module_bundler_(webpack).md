# MODULE BUNDLER (WEBPACK)

Organizes and combines multiple JS files into one. Framework like React or Angular handles bundling automatically, only needed if building from scratch.

## Install

As development dependencies:

```sh
npm i webpack webpack-cli -D
```

## Usage

Module bundler looks for entry point, root of JS code that usually imports everything. And specify output folder:

```sh
node_modules/.bin/webpack --entry ./src/index.js -o dist
```

Tip: If entry point is `src/index.js` and output is `dist/main.js`, just need:

```sh
node_modules/.bin/webpack
```

## Source Map

Webpack makes code unreadable. To help debugging, generate **source map**.

Add `webpack.config.js` at root with content:

```js
const path = require('path');

module.exports = {
  mode: 'development',
  devtool: 'eval-source-map',
  entry: './src/index.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  }
}
```

Run bundler again. Will generate `bundle.js`. Change to it in html. Can now debug source in devtool as usual.
