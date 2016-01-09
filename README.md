## Webpack-Babel

```
npm init
npm install webpack babel-loader babel-core babel-preset-es2015 --save-dev
```

### package.json

``` json

{
  "name": "webpack-babel",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "npm run build:js",
    "build:js": "webpack",
    "prewatch": "npm run build",
    "watch": "npm run watch:js",
    "watch:js": "webpack --watch"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "babel-core": "^6.4.0",
    "babel-loader": "^6.2.1",
    "babel-preset-es2015": "^6.3.13",
    "webpack": "^1.12.10"
  }
}

```

### webpack.config.js

``` javascript

module.exports = {
  entry: "./src/main.js",
  output: {
    path: __dirname,
    filename: "bundle.js"
  },
  module: {
    loaders: [
      {
        test: /\.js$/,
        exclude: /(node_modules|bower_components|bundle\.js)/,
        loader: 'babel-loader',
        query: {
          presets: ['es2015']
        }
      }
    ]
  }
};

```
