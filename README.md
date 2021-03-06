# Magnificent.js

> Zoom responsively. A jQuery plugin for responsive zoom of images & more!

[![NPM version](https://badge.fury.io/js/magnificent.svg)](http://badge.fury.io/js/magnificent)
[![Bower](https://img.shields.io/bower/v/magnificent.svg)](https://github.com/AndersDJohnson/magnificent.js)
 [![Build Status](https://travis-ci.org/AndersDJohnson/magnificent.js.svg)](https://travis-ci.org/AndersDJohnson/magnificent.js) 

[![NPM](https://nodei.co/npm/magnificent.png)](https://nodei.co/npm/magnificent/)


[![Join the chat at https://gitter.im/AndersDJohnson/magnificent.js](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/AndersDJohnson/magnificent.js?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Table of Contents

<!-- toc -->

- [Demo](#demo)
- [Features](#features)
  * [2.0](#20)
  * [2.1](#21)
  * [2.2](#22)
- [Install](#install)
  * [Bower](#bower)
  * [npm](#npm)
  * [Manual](#manual)
- [Usage](#usage)
  * [Load](#load)
  * [Integrate](#integrate)
- [Analytics](#analytics)
- [Contributing](#contributing)
  * [Build Docs](#build-docs)
  * [Tests](#tests)
- [v1.x](#v1x)
- [Alternatives](#alternatives)
- [License](#license)

_(Table of contents generated by [verb])_

<!-- tocstop -->

## Demo

Check out the [demo][mag-demo]! Or the `data-*` attributes [demo][mag-demo-data].

## Features

### 2.0

* Scroll-to-zoom
* Drag interaction
* Inline option
* Control buttons
* Different proportions for thumb vs. zoom
* CSS 3D transforms
* Full screen (coming soon)
* Event support, e.g. for stats/HUDs

### 2.1

* Touch interaction (pan, pinch)
* [Analytics](#analytics)
* Stabilized scroll-to-zoom, better for touchpads

### 2.2

* Support `data-*` attributes for [#37](https://github.com/AndersDJohnson/magnificent.js/issues/37).

## Install

### Bower

Install with [bower](http://bower.io/)

```sh
$ bower install magnificent --save
```

### npm

Install with [npm](https://www.npmjs.com/)

```sh
$ npm i magnificent --save
```

### Manual

[Download manually](https://github.com/AndersDJohnson/magnificent.js/releases).


## Usage

1. [Load](#load)
2. [Integrate](#integrate)

### Load

If you're using AMD or Browersify, you'll probably just want to specify any main files you need, e.g. `src/js/mag-jquery.js`, as dependencies in your script(s).

You'll also want to include the CSS files below in your page.

Otherwise, you'll have to include individually in your page any main files you need, preceded by their dependencies.

* First, any dependencies of any main files you need:

  * [jquery](https://github.com/jquery/jquery-dist)@[~2.1.3](https://github.com/jquery/jquery-dist/tree/2.1.4)
    * [bower_components/jquery/dist/jquery.js](https://raw.githubusercontent.com/jquery/jquery-dist/2.1.4/dist/jquery.js)
  * [jquery-bridget](https://github.com/desandro/jquery-bridget)@[~1.1.0](https://github.com/desandro/jquery-bridget/tree/v1.1.0)
    * [bower_components/jquery-bridget/jquery.bridget.js](https://raw.githubusercontent.com/desandro/jquery-bridget/v1.1.0/jquery.bridget.js)
  * [jquery-mousewheel](https://github.com/jquery/jquery-mousewheel)@[~3.1.12](https://github.com/jquery/jquery-mousewheel/tree/3.1.13)
    * [bower_components/jquery-mousewheel/jquery.mousewheel.js](https://raw.githubusercontent.com/jquery/jquery-mousewheel/3.1.13/./jquery.mousewheel.js)
      * Optional: For scroll/touchpad-pinch zoom.
  * [jquery.threedubmedia](https://github.com/threedubmedia/jquery.threedubmedia)@[*](https://github.com/threedubmedia/jquery.threedubmedia/tree/master)
    * [bower_components/jquery.threedubmedia/event.drag/jquery.event.drag.js](https://raw.githubusercontent.com/threedubmedia/jquery.threedubmedia/master/event.drag/jquery.event.drag.js)
      * Optional: For drag interaction.
  * [screenfull](https://github.com/sindresorhus/screenfull.js)@[~2.0.0](https://github.com/sindresorhus/screenfull.js/tree/v2.0.0)
    * [bower_components/screenfull/dist/screenfull.js](https://raw.githubusercontent.com/sindresorhus/screenfull.js/v2.0.0/dist/screenfull.js)
      * Optional: For fullscreen.
  * [google-analytics-js](https://github.com/adjohnson916/google-analytics-js)@[^0.1.0](https://github.com/adjohnson916/google-analytics-js/tree/0.1.1)
    * [bower_components/google-analytics-js/gajs.js](https://raw.githubusercontent.com/adjohnson916/google-analytics-js/0.1.1/gajs.js)
      * Optional: For analytics. Please :).
  * [hammerjs](https://github.com/EightMedia/hammer.js)@[~2.0.4](https://github.com/EightMedia/hammer.js/tree/v2.0.8)
    * [bower_components/hammerjs/hammer.js](https://raw.githubusercontent.com/EightMedia/hammer.js/v2.0.8/hammer.js)
      * Optional: For touch interaction (pan, pinch).
  * [prevent-ghost-click](https://github.com/adjohnson916/prevent-ghost-click.js)@[~0.0.0](https://github.com/adjohnson916/prevent-ghost-click.js/tree/v0.0.0)
    * [bower_components/prevent-ghost-click/PreventGhostClick.js](https://raw.githubusercontent.com/adjohnson916/prevent-ghost-click.js/v0.0.0/PreventGhostClick.js)
      * Optional: For touch interaction (pan, pinch).


```html
<script src="bower_components/jquery/dist/jquery.js"></script>
<script src="bower_components/jquery-bridget/jquery.bridget.js"></script>
<script src="bower_components/jquery-mousewheel/jquery.mousewheel.js"></script>
<script src="bower_components/jquery.threedubmedia/event.drag/jquery.event.drag.js"></script>
<script src="bower_components/screenfull/dist/screenfull.js"></script>
<script src="bower_components/google-analytics-js/gajs.js"></script>
<script src="bower_components/hammerjs/hammer.js"></script>
<script src="bower_components/prevent-ghost-click/PreventGhostClick.js"></script>
```


* Then, any main files you need:

  * [src/js/mag-analytics.js](src/js/mag-analytics.js)
    * Optional: For analytics. Please :).
  * [src/js/mag.js](src/js/mag.js)
  * [src/js/mag-jquery.js](src/js/mag-jquery.js)
  * [src/js/mag-control.js](src/js/mag-control.js)
    * Optional: For controls.
  * [src/css/mag.css](src/css/mag.css)
  * [src/theme/default.css](src/theme/default.css)
    * Optional: Or another theme.


```html
<script src="bower_components/magnificent/src/js/mag-analytics.js"></script>
<script src="bower_components/magnificent/src/js/mag.js"></script>
<script src="bower_components/magnificent/src/js/mag-jquery.js"></script>
<script src="bower_components/magnificent/src/js/mag-control.js"></script>
<link rel="stylesheet" href="bower_components/magnificent/src/css/mag.css" />
<link rel="stylesheet" href="bower_components/magnificent/src/theme/default.css" />
```



### Integrate

See usage examples in [demo][mag-demo].
Also the [JSDoc][mag-jsdoc], especially [options][mag-jsdoc-opts].


## Analytics

This component includes tracking via Google Analytics.
The purpose is to better understand how and where it's used, as a guide for development.

To opt-out of this tracking, before loading the script on your page,
use the global options in JavaScript, with `noTrack` set to `true`, as follows:

```js
window.MAGNIFICENT_OPTIONS = {
  noTrack: true
};
```


## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/AndersDJohnson/magnificent.js/issues/new).


In lieu of a formal styleguide, please:
 - Take care to maintain the existing coding style
 - Add unit tests for any new or changed functionality
 - Re-build documentation with [verb-cli](https://github.com/assemble/verb-cli) before submitting a pull request.


### Build Docs

Install dev dependencies, then run [verb]:

```js
$ npm install -d && verb
```

[verb]: https://github.com/verbose/verb

### Tests

Install dev dependencies:

```sh
$ npm i -d && npm test
```

## v1.x

See https://github.com/AndersDJohnson/magnificent.js/tree/v1.x.

## Alternatives

* [Magnifier.js]
* [ElevateZoom]

## License
Copyright © 2013-2017 [Anders D. Johnson](https://github.com/AndersDJohnson).
Released under the MIT license.


***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on September 02, 2017._

[mag-demo]: http://AndersDJohnson.github.io/magnificent.js/examples/demo/
[mag-demo-data]: http://AndersDJohnson.github.io/magnificent.js/examples/demo/index-data.html
[mag-jsdoc]: http://AndersDJohnson.github.io/magnificent.js/docs/jsdoc/
[mag-jsdoc-opts]: http://AndersDJohnson.github.io/magnificent.js/docs/jsdoc/global.html#MagnificentOptions
[bower]: http://bower.io/
[Magnifier.js]: http://mark-rolich.github.io/Magnifier.js/
[ElevateZoom]: http://www.elevateweb.co.uk/image-zoom
