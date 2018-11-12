# @stackr23/styleobjects-loader
> **load StyleSheets as JS-Objects** (webpack-loader)

[![Build Status](https://travis-ci.com/stackr23/styleobjects-loader.svg?branch=master)](https://travis-ci.com/stackr23/styleobjects-loader)
[![npm version](https://badge.fury.io/js/%40stackr23%2Fstyleobjects-loader.svg?v080)](https://badge.fury.io/js/%40stackr23%2Fstyleobjects-loader)
[![devDependencies Status](https://david-dm.org/stackr23/styleobjects-loader/dev-status.svg)](https://david-dm.org/stackr23/styleobjects-loader?type=dev)
[![Known Vulnerabilities](https://snyk.io/test/github/stackr23/styleobjects-loader/badge.svg)](https://snyk.io/test/github/stackr23/styleobjects-loader) [![Greenkeeper badge](https://badges.greenkeeper.io/stackr23/styleobjects-loader.svg)](https://greenkeeper.io/)<br />
[![Maintenance][maintenance-img]][maintenance-url]
[![PRs Welcome][pr-welcome]](http://makeapullrequest.com)

[maintenance-img]: https://img.shields.io/badge/Maintained%3F-yes-green.svg
[maintenance-url]: https://GitHub.com/stackR23/styleobjects-loader/graphs/commit-activity
[pr-welcome]: https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square

## v0.7.0 released  
> __stable version with webpack 4 compatibility__  

### usage
```npm install @stackr23/styleobjects-loader --save-dev```

__your.csso__
```Stylus
.test23
  font-size 23px
  .testInner
    font-decoration none
```

__your.js__  
```Javascript
import styleobject from '@stackr23/styleobjects-loader!stylus-loader!./your.csso'
```

__styleobject__
```Javascript
{
  test23: {
  'fontSize': '23px',
  testInner: {'fontDecoration': 'none'}
}
```

### advanced usage

> for __ES6/7 usage__, define loaders in the webpack config  
```Javascript
// webpack.config.js
module: {rules: [...yourLoaders, {
  test:   /\.(csso)$/,
  use:    ['@stackr23/styleobjects-loader', 'stylus-loader']
}]}
// yourComponent.js
import yourStyleObject from '/styles/your.csso'
```

> for __other style preprocessor__ syntax (less, sass, scss, ...)
> just add the realated loader (the loader has to output css!)
```Javascript
let style = require('@stackr23/styleobjects-loader!sass-loader!./your.sass');
```

> for __pure css__ just use
```Javascript
let style = require('@stackr23/styleobjects-loader!./your.css');
```

### v1 roadmap  
* [ ] stackr23/styleobjects#3 
* [ ] handle loader options
* [ ] ES6 (/dist + buildScript)

### issues
* for objectformat and enhanced usage go to [styleobjects](https://github.com/stackr23/styleobjects)
* webpack/loader related issues or PR's are welcome
