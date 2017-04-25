detect-element-resize
=====================

This is an [npm package](https://docs.npmjs.com/getting-started/what-is-npm) for a javascript library to detect when an element on the page changes its size. This repo is a very thin wrapper over [this excellent bit of code](https://github.com/sdecima/javascript-detect-element-resize) by [Sebastián Décima](https://github.com/sdecima), with some modifications.

# How to Use this Software
*This repository is just an npm package. If you're not using npm, please look at [the original repo](https://github.com/sdecima/javascript-detect-element-resize) for installation notes.*

## Installation
To add this library to our npm project, we run the command:

``` bash
npm install --save detect-element-resize
```

## Usage

First, we make a file `require()`-ing the package:

*your-code.js*

``` javascript
var DetectElementResize = require('detect-element-resize');

var targetElement = document.getElementById('element-to-watch');

var resizeCallback = function () {
  var elementResized = this;
  console.log('element #' + elementResized.id + ' was resized!');
};

DetectElementResize.addResizeListener(targetElement, resizeCallback);
// resizeCallback will now be called whenever the dimensions of targetElement change
// ...
DetectElementResize.removeResizeListener(targetElement, resizeCallback);
// resizeCallback is no longer triggered

// more code ...
```

Now we run the [browserify](http://browserify.org/) command to generate the browser-ready *bundle.js*:

``` bash
browserify -r your-code.js -o bundle.js
```

And we include it in our webpage:

*index.html*

``` html
<!-- ... -->
<script type="text/javascript" src="bundle.js"></script>
<!-- ... -->
<div id="element-to-watch"></div>
<!-- ... -->
```

Watch the console output as you resize the element!

# License
## Contact
Contact me [here](https://github.com/cosmicexplorer).

## This Program
If the license for a file in this repository is not clearly and specifically denoted within the file or another file in the same directory, it is licensed under the GNU GPL version 3 (or any later version) as specified in [GPL.md](GPL.md).

## External
Any code under the [external/](external) subdirectory has its own *README.md* and *LICENSE* files, which are also listed below for convenience. Please [make an issue](https://github.com/cosmicexplorer/detect-element-resize/issues/new) if you believe this repository violates the licenses of any external code.

- [javascript-detect-element-resize](external/javascript-detect-element-resize): [MIT](external/javascript-detect-element-resize/LICENSE)
