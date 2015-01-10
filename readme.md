# strip-css-comments [![Build Status](https://travis-ci.org/sindresorhus/strip-css-comments.svg?branch=master)](https://travis-ci.org/sindresorhus/strip-css-comments)

> Strip comments from CSS

Also available as a [gulp](https://github.com/sindresorhus/gulp-strip-css-comments)/[grunt](https://github.com/sindresorhus/grunt-strip-css-comments)/[broccoli](https://github.com/sindresorhus/broccoli-strip-css-comments) plugin.


## Usage

```sh
$ npm install --save strip-css-comments
```

```js
var stripCssComments = require('strip-css-comments');

stripCssComments('/*! <copyright> */ body { /* unicorns */color: hotpink; }');

```


## API

### `stripCssComments(input[, options])`

Returns a `String` without any CSS comments according to the options described below.

```js
stripCssComments('body { /* unicorns */color: hotpink; }');
//=> body { color: hotpink; }
``` 


## Options

All options are optionals and set up with usable defaults. Change them according to your needs.

### `all`

`Boolean` indicates if "important" CSS comments (beginning with the characters `/*!`) should be also striped in the output.

Default value is `false`.

```js
stripCssComments('/*! <copyright> */ body { /* unicorns */color: hotpink; }');
//=> /*! <copyright> */ body { color: hotpink; }

stripCssComments('/*! <copyright> */ body { /* unicorns */color: hotpink; }', {all: true});
//=> body { color: hotpink; }
``` 


## CLI

```sh
$ npm install --global strip-css-comments
```

```
$ strip-css-comments --help

  Usage
    strip-css-comments <input-file> > <output-file>
    strip-css-comments < <input-string>

  Option
  	-a, --all strip all comments without any exceptions

  Example
    strip-css-comments src/app.css > dist/app.css
    strip-css-comments < src/app.css --all
```


## Benchmark

```sh
$ npm run bench
```


## Related

- [`strip-json-comments`](https://github.com/sindresorhus/strip-json-comments)


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
