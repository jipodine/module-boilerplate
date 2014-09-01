## Gulp commands

* `gulp` - build the lib in root folder : transpile es6 -> es5 and make standalone and uglify version
* `gulp --transpile=no` - build the lib in "build" folder without transpiling
* `gulp test` - build standalone lib and dependencies and launch server on 9001 port for unit testing
* `gulp init-docs` - create "docs" and "partials" folder with empty "_api.md", "_demo-ghp.md" files
* `gulp get-docs-options` - get "options.json" to "docs" folder
* `gulp get-docs-readme` -  get "README.tmpl.md" to "docs" folder
* `gulp get-docs-index` - push "index.tmpl.html" to "docs" folder
* `gulp docs` - create README.md
* `gulp gh-pages` - create gh-pages
* `gulp serve-gh-pages` - test your gh-pages online on 9002 port
* `gulp deploy-gh-pages` - push gh-pages folder to github
* `gulp export-examples` - create examples folder with gh-pages demo
* `gulp serve-examples` - test your examples online on 9003 port

## Package.json

Add this dependencies in your repo

```js
"devDependencies": {
  "module-boilerplate": "git://github.com/Ircam-RnD/module-boilerplate.git#master",
  "fs-utils" : "0.4.3",
  "browserify": "~4.1.2",
  "mocha": "~1.17.1",
  "chai": "~1.9.0",
  "blanket": "~1.1.6",
  "gulp": "~3.8.2"
}
```

## .gitignore

```
/node_modules/*
/gh-pages/*
```

## gulpfile.js

```js
var gulp = require('gulp');
var packageJson = require('./package.json');
var loadTasks = require('module-boilerplate');

loadTasks(gulp, packageJson);
```

## options.json

```js
{
  "cdn" : "https://rawgit.com",
  "css" : {
    "external" : [
      {"cdn": true, "url": "/Ircam-RnD/module-boilerplate/master/docs/css/main.css"}
    ],
    "internal": []
  },
  "js" : {
  	"external" : [
      {"url": "//cdnjs.cloudflare.com/ajax/libs/highlight.js/8.0/highlight.min.js"},
      {"cdn": true, "ircamlib" : true, "url": "player"},
      {"cdn": true, "ircamlib" : true, "url": "buffer-loader"}
    ],
    "internal": []
  }
}
```
