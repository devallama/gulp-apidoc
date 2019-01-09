# [gulp](https://github.com/gulpjs/gulp)-apidoc

Generates a RESTful web API Documentation using the [apidoc](https://github.com/apidoc/apidoc) library.

## How It Works

`/path/api/stuff.js`:

```js
/**
 * @api {get} /user/:id Request User information
 * @apiName GetUser
 * @apiGroup User
 *
 * @apiParam {Number} id Users unique ID.
 *
 * @apiSuccess {String} firstname Firstname of the User.
 * @apiSuccess {String} lastname  Lastname of the User.
 */
```

## Install

Install with GitHub:

```cli
npm install --save-dev devallama/gulp-apidoc
```

Soon to be on NPM (hopefully).

## Usage

```shell
const gulp = require('gulp'),
    apidoc = require('gulp-apidoc');

gulp.task('apidoc', function(done) {
    apidoc({
        src: "example/",
        dest: "build/"
    }, done);
});
```

With options:

```js
const gulp = require('gulp'),
    apidoc = require('gulp-apidoc');

gulp.task('apidoc', function(done) {
    apidoc({
        src: "example/",
        dest: "build/",
        template: "template/",
        debug: true,
        config: "configurations/",
        includeFilters: [ ".*\\.js$" ]
    }, done);
});
```

Other options [checkout](https://github.com/apidoc/apidoc/blob/master/lib/index.js#L14-L21).

## Options

#### options.src

The folder to scan for apidoc documentation.

Type: `String`

#### options.dest

The folder where to output the generated files.

Type: `String`
Default: `doc/`

#### options.template

Custom template to use for the output files.

Type: `String`

#### options.config

Type: `String`
Default: `options.src`

#### options.debug

Type: `Boolean`
Default: `false`

#### options.silent

Type: `Boolean`
Default: `false`

#### options.verbose

Type: `Boolean`
Default: `false`

#### options.simulate

Type: `Boolean`
Default: `false`

#### options.includeFilters

Type: `Array`
Default: `[]`

---
Forked from [c0b41/gulp-apidoc](https://github.com/c0b41/gulp-apidoc)