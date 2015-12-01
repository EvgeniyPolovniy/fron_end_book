# Pre- and Post- processors
**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**

### Pre-processors
[SASS](http://sass-lang.com) (Syntactically Awesome Stylesheets) — модуль, включенный в Haml. Sass — это метаязык на основе CSS, предназначенный для увеличения уровня абстракции CSS кода и упрощения файлов каскадных таблиц стилей.

[LESS](http://lesscss.org) — это динамический язык стилей, который разработал Alexis Sellier. Он создан под влиянием языка стилей Sass, и, в свою очередь, оказал влияние на его новый синтаксис «SCSS», в котором также использован синтаксис, являющийся расширением СSS.

[SASS vs LESS (Habrahabr post)](http://habrahabr.ru/post/144309)

### Post-processor
[PostCss](https://github.com/postcss/postcss) - это инструмент, для изменения Css с помощью JavaScript. Это нечто большее чем простой пост-процессор, но и немного не то, чем являются препроцессоры.

##SCSS (синтаксис SASS)
### Вложенность
SCSS
```scss
#some {
  border: 1px solid red;
  .some { background: white; }
}
```
CSS
```css
#some {
  border: 1px solid red;
}
#some .some {
  background: white;
}
```
### Переменные и операции с ними
SCSS
```scss
$blue: #3bbfce;
$margin: 16px;
$url: url(../img/icons/ui-ios-sprite.png);

.content-navigation {
  border-color: $blue;
  color: darken($blue, 9%);
}
.border {
  padding: $margin / 2;
  margin: $margin / 2;
  border-color: $blue;
}
.wrapper {
  background: $url;
}
```
CSS
```css
.content-navigation {
  border-color: #3bbfce;
  color: #2ca2af;
}
.border {
  padding: 8px;
  margin: 8px;
  border-color: #3bbfce;
}
.wrapper {
  background: url(../img/icons/ui-ios-sprite.png);
}
```
### Подключение других scss файлов
SCSS
```scss
@import "./core/variables";
@import "./core/mixin";
@import "./core-project/variables";
```

### Миксинны
Переменные в миксинах поддерживают default значания.
SCSS
```scss
@mixin text-truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
@mixin transition( $transition-property, $transition-time, $transition-method:  ease) {
  -webkit-transition: $transition-property $transition-time $transition-method;
  -moz-transition: $transition-property $transition-time $transition-method;
  -ms-transition: $transition-property $transition-time $transition-method;
  -o-transition: $transition-property $transition-time $transition-method;
  transition: $transition-property $transition-time $transition-method;
}

.block-wrap {
  .block {
    @include text-truncate;
  }
  @include transition(all, .2ms);
}
```
CSS
```css
.block-wrap {
  -webkit-transition: all 0.2ms ease;
  -moz-transition: all 0.2ms ease;
  -ms-transition: all 0.2ms ease;
  -o-transition: all 0.2ms ease;
  transition: all 0.2ms ease;
}
.block-wrap .block {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}
```
### Наследование
SCSS
```scss
%extend_1 {
  display: inline-block;
}
%extend_2 {
  @extend %extend_1;
  width: 34px;
  height: 19px;
}
.wrap {
  @extend %extend_1;
  .block {
    @extend %extend_2;
  }
}
```
CSS
```css
.wrap,
.wrap .block {
  display: inline-block;
}
.wrap .block {
  width: 34px;
  height: 19px;
}
```
**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**