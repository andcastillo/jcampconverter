# JCAMP converter

  [![NPM version][npm-image]][npm-url]
  [![build status][travis-image]][travis-url]
  [![npm download][download-image]][download-url]

Parse and convert JCAMP data

## Installation

### Node JS

`npm install jcampconverter`

### Bower

`bower install jcampconverter`

## Methods

### convert(jcamp, [options], [useWorker])

Converts the `jcamp` using `options`.

__Arguments__

* `jcamp` - String containing the JCAMP data
* `options` - Object with options to pass to the converter
* `useWorker` - Browser only: convert in a web worker (default: false). If this option is set to true, it will return a [Promise](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Promise).

__Options__

* keepSpectra - Generate array for 2D NMR spectra (default: false)
* keepRecordsRegExp - regexp to select which records should be placed in the info field. By default: :/^$/} (nothing is kept)
* xy - instead of creating a 1D array containing [x1,y1,x2,y2, ...] create an object: {x:[], y:[]}


### Use as a module

#### Node JS

```javascript
var converter = require('jcampconverter');
var jcamp = require('fs').readFileSync('path/to/jcamp.dx').toString();

var result = converter.convert(jcamp);
```

#### AMD

```javascript
require(['jcampconverter'], function(JcampConverter) {
    // Use the worker
    JcampConverter.convert(jcamp, true).then(function (result) {
        // Do something with result
    });
});
```

## Testing and build

```
npm install
npm test
npm run build
```

## Benchmark

```
npm run benchmark
```

## How to create the tests

http://unitjs.com/guide/should-js.html

## License

  [MIT](./LICENSE)

[npm-image]: https://img.shields.io/npm/v/jcampconverter.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/jcampconverter
[travis-image]: https://img.shields.io/travis/cheminfo-js/jcampconverter/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/cheminfo-js/jcampconverter
[download-image]: https://img.shields.io/npm/dm/jcampconverter.svg?style=flat-square
[download-url]: https://www.npmjs.com/package/jcampconverter
