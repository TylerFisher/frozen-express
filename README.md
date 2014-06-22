# Frozen Express

Frozen Express generates a collection of static files for an Express.js application allowing to host said application easily and cheaply.

Express 4 and Express 3 applications are supported.

[![Build Status](https://travis-ci.org/denis-sokolov/frozen-express.svg?branch=master)](https://travis-ci.org/denis-sokolov/frozen-express)
[![Code Climate](http://img.shields.io/codeclimate/github/denis-sokolov/frozen-express.svg)](https://codeclimate.com/github/denis-sokolov/frozen-express)
[![Coverage Status](https://img.shields.io/coveralls/denis-sokolov/frozen-express.svg)](https://coveralls.io/r/denis-sokolov/frozen-express?branch=master)
[![Dependency Status](https://gemnasium.com/denis-sokolov/frozen-express.svg)](https://gemnasium.com/denis-sokolov/frozen-express)

## Usage

```javascript
var frozen = require('frozen-express');

var stream = frozen(app);
```

You can do with the generated `Stream` whatever you want, but the simplest thing is to use `gulp-dest`:

```javascript
var gulp = require('gulp');
var frozen = require('frozen-express');

frozen(app).pipe(gulp.dest('./dist'));
```

You can also include it in your Gulp workflow and perform more tasks with files.

### Options

Frozen Express supports a number of options:

```javascript
var stream = frozen(app, {
    // Add control files for serving the application with a particular server
    // Valid options: 'apache'
    server: false,

    // A list of URLs to freeze
    // By default Frozen will try to detect the URLs itself
    urls: ['/', '/about', '/contact']
});
```
