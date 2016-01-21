# Ember Webpack Loaders

A set of webpack loaders to help with ember integration.
Check the example app here: https://github.com/tulios/ember-webpack-example

## Install

```sh
npm install ember-webpack-loaders
```

## Usage

Apply this set of loaders to your `webpack.config.js`:

```js
{
  module: {
    loaders: [
      {
        test: /\.hbs$/,
        include: /app\/templates/, // or whatever directory you have
        loader: 'ember-webpack-loaders/htmlbars-loader'
      },
      {
        test: /app\/index\.js/, // the main app file
        loader: 'ember-webpack-loaders/inject-templates-loader!ember-webpack-loaders/inject-modules-loader'
      }
    ]
  }
}
```

## Options

### ember-webpack-loaders/htmlbars-loader

* _appPath_: Path for your ember app. Default assuming `webpack.config.js` in root folder and `./app`
* _templateCompiler_: default 'components-ember/ember-template-compiler.js'

### ember-webpack-loaders/inject-templates-loader

* _appPath_: Path for your ember app. Default assuming `webpack.config.js` in root folder and `./app`

### ember-webpack-loaders/inject-modules-loader

* _appPath_: Path for your ember app. Default assuming `webpack.config.js` in root folder and `./app`
* _appVar_: Variable name of your `Ember.Application`. Default `App`

Example:

```js
{
  module: {
    loaders: [
      {
        test: /app\/index\.js/,
        loader: 'ember-webpack-loaders/inject-templates-loader!ember-webpack-loaders/inject-modules-loader',
        query: {
          appVar: 'MyProject'
        }
      }
    ]
  }
}
```

## License

See [LICENSE](https://github.com/tulios/ember-webpack-loaders/blob/master/LICENSE) for more details.
