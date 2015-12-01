# CSS
**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**

Основные правила чистоты кода
```css
/* Плохой CSS */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* Хороший CSS */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin: 0 0 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```
Используйте class
```css
/* Плохой CSS */
ul li { }
#element { }

/* Хороший CSS */
.list-item { }
.element { }
```
Очень важный код :)
```css
/* Плохой CSS */
.dropdown {
    padding: 10px !important;
    opacity: 0.9 !important;
}
/* Хороший CSS */
.dropdown_cute {
    padding: 10px;
    opacity: 0.9;
}
```
Стили для тегов это плохо
```css
/* Плохой CSS */
body ul li {
    line-height: 20px;
}
/* Хороший CSS */
.item {
    line-height: 20px;
}
```

# HTML
**[Table of Contents](#table-of-contents)**

Именование классов.
Исключение методология БЭМ
```css
/* Плохо */
.pageHead {}
.sub_content {}
.tmp_block-footerWrap {}

/* Хорошо */
.page-head {}
.sub-content {}
```
Для JS пишите отдельные классы и не вешайте на них стили из css
```css
.js-item
.action-save
```
Именование файлов
```css
/* Плохо */
ios-icon.png
ios-icon2x.png
mainSprite.png

/* Хорошо */
ios_icons.png
ios_icons@2x.png
main_sprite_app.png
```
#### Оптимизация картинок
1. PNG только для картинок с прозрачностью.
2. png-24 не всегда оплавданно, png-8 значительно легче
3. При нарезке в PS сохранять только в web формате (ctrl+shift+alt+s) и в 100% качества
4. Все картинки сохранять с кодировкой progressive
5. Использовать сервисы оптимизации изображений перед релизом.

**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**