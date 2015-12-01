#Project Builders
**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**

[Gulp](http://gulpjs.com), [Grunt](http://gruntjs.com/) — это инструменты сборки веб-приложения, позволяющиe автоматизировать повторяющиеся задачи, такие как сборка и минификация CSS- и JS-файлов, запуск тестов, перезагрузка браузера и т.д

[Webpack](http://webpack.github.io) — это утилита для сборки бандлов и оптимизации модулей JavaScript и других ресурсов для фронтенда.

Основное отличие Gulp/Grunt от Webpack в том, что первые построенны на логике выполнения задачь, а webpack создает "модули", которыми и оперирует.

Дальше рассмотрим подробнее Gulp на примере одного из наших проектов.

##Gulp
projectBasePath/package.json

![](docs/gulp1.png)

```json
{
  "name": "tishman",
  "version": "1.0.0",
  "description": "",
  "main": "build.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "repository": {
    "type": "git",
    "url": "git@gitlab.a2a.co:webinerds/tishman.git"
  },
  "author": "Max Klishevych",
  "license": "ISC",
  "devDependencies": {
    "del": "^1.2.0",
    "gulp": "^3.8.11",
    "gulp-concat": "^2.5.2",
    "gulp-order": "^1.1.1",
    "gulp-resolve-dependencies": "^2.1.0",
    "gulp-sass": "^2.0.1",
    "require-dir": "^0.3.0"
  }
}
```

projectBasePath/gulpfile.js
```js
require('./ichannel-base/gulpfile.js'); 
```

projectBasePath/ichannel-base/gulpfile.js
```js
var requireDir = require('require-dir');
// Require all tasks in gulp/tasks, including sub folders
requireDir('./gulp/tasks', { recurse: true });
```

projectBasePath/ichannel-base/gulp/config.js
```js
module.exports = {
    files: {
        scss: {
            base: './ichannel-base/assets/scss/**/*.scss',
            project: './assets/scss/**/*.scss',
            mergeFolder: './merged-scss',
            buildName: 'build.css',
            compileFolder: './compiled-css',
            buildFolder: './public/css',
            concatFilesOrder: [
                'global.scss',
                'global-*.scss'
            ]
        },
        fonts: {
            project: './assets/fonts/**/**',
            buildFolder: './public/fonts'
        },
        img: {
            base: './ichannel-base/assets/img/**/**',
            project: './assets/img/**/**',
            buildFolder: './public/img'
        },
        js: {
            base: './ichannel-base/js/**/*.js',
            project: './js/**/*.js',
            buildName: 'build.js',
            buildFolder: './public/js',
            mergeFolder: './merged-js',
            concatFilesOrder: [
                'constants.js',
                'config-base.js',
                'config.js',
                'app.js',
                'utils/*',
                'services/*',
                'controllers/**/**',
                'ui/*',
                'views/**/**',
                'bootstrap.js'
            ]
        },
        views: {
            base: './ichannel-base/views/**/*.html',
            project: './views/**/*.html',
            buildName: 'index.html',
            buildFolder: '.',
            mergeFolder: './merged-html',
            concatFilesOrder: [
                'index.start.html',
                'body.html',
                'templates/**/**',
                'index.end.html'
            ]
        }
    }
};
```

#### Путь одной таски
Запуск сборщика

```
E:\OpenServer\domains\jen.a2a.co>gulp
```

projectBasePath/ichannel-base/gulp/tasks/dafault.js
```js
var gulp = require('gulp');

gulp.task('default', [
    'js:default',
    'scss:default',
    'img:default',
    'views:default',
    'fonts:default'
]);
```

projectBasePath/ichannel-base/gulp/tasks/sscss:default.js
```js
var gulp = require('gulp');

gulp.task('scss:default', ['scss:merge', 'scss:concat', 'scss:compile', 'scss:cleanup']);
```

Одна из задачь - сборка scss
projectBasePath/ichannel-base/gulp/tasks/scss-compile.js
```js
var gulp = require('gulp');
var sass = require('gulp-sass');
var config = require('../config');

gulp.task('scss:compile', ['scss:merge'], function (cb) {
    var stream = gulp
        .src([config.files.scss.mergeFolder + '/**/**'])
        .pipe(sass().on('error', sass.logError))
        .pipe(gulp.dest(config.files.scss.compileFolder))
    ;

    stream.on('end', function () {
        cb();
    });
});
```

Выполнение сборки проекта

![](docs/gulp.gif)

**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**