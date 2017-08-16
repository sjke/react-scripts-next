# react-scripts-next
Latest version of original ```react-scripts```: **1.0.11**

### Disclaimer:
> This is fork of ```react-scripts``` from ```create-react-app```. It provides simple way to modify webpack config without ejecting.

### How to use it
```create-react-app my-app --scripts-version react-scripts-next```

Modify the ```./config/web pack.config.[ENV].js``` file in the root of the generated project and add any of the configuration options that you want.

### Available Configuration options
- ```babel plugins```
- ```babel presets```
- ```webpack loaders```
- ```webpack plugins```

#### A few examples:

##### Adding ``less`` support for ```create-react-appp```
1. Execute command:
```bash
npm install --save-dev less-loader less
```
2. Modify ```./config/web pack.config.[ENV].js```
```javascript
module.exports = {
  babelPlugins: [],
  babelPresets: [],
  webpackLoaders: [
    {
      test: /\.less$/,
      use: [{
        loader: 'style-loader',
      }, {
        loader: 'css-loader',
      }, {
        loader: 'less-loader',
      }],
    },
  ],
  webpackPlugins: [],
};
```

##### Adding ``babel-preset-stage-0`` support for ```create-react-appp```
1. Execute command:
```bash
npm install --save-dev babel-preset-stage-0
```
2. Modify ```./config/web pack.config.[ENV].js```
```javascript
module.exports = {
  babelPlugins: [],
  babelPresets: [require.resolve('babel-preset-stage-0')],
  webpackLoaders: [],
  webpackPlugins: [],
};
```
