# gulp-raml2html [![Build Status](https://travis-ci.org/walling/gulp-raml2html.svg?branch=master)](https://travis-ci.org/walling/gulp-raml2html) [![NPM version](https://badge.fury.io/js/gulp-raml2html.png)](http://badge.fury.io/js/gulp-raml2html) [![Dependency Status](https://gemnasium.com/walling/gulp-raml2html.png)](https://gemnasium.com/walling/gulp-raml2html)

A simple [gulp](http://gulpjs.com/) plugin to automate the process of generating HTML documentation based on a RAML API.

*If you have any difficulties with the output of this plugin, please use the [raml2html tracker](https://github.com/kevinrenskers/raml2html/issues).*

###Install via [npm](https://npmjs.org/package/gulp-raml2html):

```
npm install gulp-raml2html --save-dev
```

**Note**: This plugin wraps [raml2html](https://github.com/kevinrenskers/raml2html).

## Usage

###gulp basis
Gulp is a build life-cycle tool. You can configure several tasks to be ran when entering `gulp [taskname]` in your console ('default' task is invoked if not specified). It can also be invoked by Continuous Integration tools.
To be able to use it, your application **must** have a `gulpfile.js` with the possible tasks configured.

A typical `gulpfile.js` will start with:

```js
var gulp = require('gulp');
var raml2html = require('gulp-raml2html');
```

## Add HTML generation task

```js
// your existing tasks
gulp.task('apidoc', function() {
  return gulp.src('api.raml')
    .pipe(raml2html())
    .pipe(gulp.dest('build'));
});
// more tasks
```

## Run

`gulp apidoc` will grab `api.raml` and generate a `build` folder with the generated HTML on it.


##Example
Included in this repository. Click [here](./example) to go to the "example" folder

## API

### supportJsonInput
Type: boolean
Default value: `false`

When set to `true` it also takes JSON files as input (generated by the RAML parser).

### https
Type: boolean
Default value: `false`

When set to `true` the `raml2html` generator will output links to the all assets over `https` protocol.

## License

The code for gulp-raml2html is licensed under the MIT license. See `license.txt` file for more info.
