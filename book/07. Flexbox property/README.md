#Flexbox property
**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**

Т.к. flexbox — это целый модуль, а не просто единичное свойство, он объединяет в себе множество свойств. Некоторые из них должны применяться к контейнеру (родительскому элементу, так называемому flex-контейнеру), в то время как другие свойства применяются к дочерним элементам, или flex-элементам.

Если обычный лейаут основывается на направлениях потоков блочных и инлайн-элементов, то flex-лейаут основывается на «направлениях flex-потока»

![](img/flexbox.png)

В основном элементы будут распределяться либо вдоль главной оси (от main-start до main-end), либо вдоль поперечной оси (от cross-start до cross-end).

- main-axis - главная ось, вдоль которой располагаются flex-элементы. Oна необязательно должна быть горизонтальной, всё зависит от свойства justify-content
- main-start | main-end - flex-элементы размещаются в контейнере от позиции main-start до позиции main-end.
- main size - ширина или высота flex-элемента в зависимости от выбранной основной величины. Основная величина может быть либо шириной, либо высотой элемента.
- cross axis - поперечная ось, перпендикулярная к главной. Её направление зависит о тнаправления главной оси.
- cross-start | cross-end - flex-строки заполняются элементами и размещаются в контейнере от позиции cross-start и до позиции cross-end.
- cross size - ширина или высота flex-элемента в зависимости от выбранной размерности равняется этой величине. Это свойство совпадает с width или  height элемента в зависимости от выбранной размерности.
 
Подробнее о всех свойствах Flexbox можно посмотреть на [frontender.info](http://frontender.info/a-guide-to-flexbox/)

Для максимальной кросбраузерности также есть очень полезный SASS mixin:

```sass
@mixin flexbox() {
  display: -webkit-box;
  display: -moz-box;
  display: -ms-flexbox;
  display: -webkit-flex;
  display: flex;
}

@mixin flex($values) {
  -webkit-box-flex: $values;
  -moz-box-flex:  $values;
  -webkit-flex:  $values;
  -ms-flex:  $values;
  flex:  $values;
}

@mixin order($val) {
  -webkit-box-ordinal-group: $val;  
  -moz-box-ordinal-group: $val;     
  -ms-flex-order: $val;     
  -webkit-order: $val;  
  order: $val;
}

.wrapper {
  @include flexbox();
}

.item {
  @include flex(1 200px);
  @include order(2);
}
```

**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**
