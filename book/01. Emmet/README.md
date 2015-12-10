#Emmet
**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**

[Emmet](http://docs.emmet.io) (предыдущее название — Zen Coding) — это набор плагинов для различных популярных текстовых редакторов, используемых для скоростного написания HTML и CSS кода.

Для преобразование аббревиатуры в код необходимо нажать клавишу TAB.

При генирации кода emmet анализирует тег родителя и если в абревиатуре не указан определенный тек, то генерируется правильный с точки зрения спецификации.

- li для ul и ol
- tr для table, tbody, thead и tfoot
- td для tr
- option для select и optgroup
- span для p

ul>.item

```html
<ul>
  <li class="item"></li>
</ul>
```

p>.text

```html
<p><span class="text"></span></p>
```

### Doctype

html:5 или ! для HTML5 doctype

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

html:xt для XHTML transitional doctype

```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en">
<head>
  <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

html:4s для HTML4 strict doctype

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
<html lang="en">
<head>
  <meta http-equiv="Content-Type" content="text/html;charset=UTF-8">
  <title>Document</title>
</head>
<body>
  
</body>
</html>
```

### class и id

div.content

span#search

section#main.user

```html
<div class="content"></div>

<span id="search"></span>

<section id="main" class="user"></section>
```

### Аттрибуты и контент

a.link[href=//google.com]{google}

img.avatar[src=./default_avatar.jpg][alt=avatar][title=avatar]

```html
<a href="//google.com" class="link">google</a>

<img src="./default_avatar.jpg" alt="avatar" class="avatar" title="avatar">
```

### Нумерация и дублирование

p*2

.list$*5

```html
<p></p>
<p></p>

<div class="list1"></div>
<div class="list2"></div>
<div class="list3"></div>
<div class="list4"></div>
<div class="list5"></div>
```

### Вложенность и структурирование

p>.count+.name

p>span^ul>.item-$*2

(.title>h1)+(.desc>h2)

```html
<p><span class="count"></span><span class="name"></span></p>

<p><span></span></p>
<ul>
  <li class="item-1"></li>
  <li class="item-2"></li>
</ul>

<div class="title">
  <h1></h1>
</div>
<div class="desc">
  <h2></h2>
</div>
```

### CSS аббревиатуры

.class {
  w50+h10p+lh2e
}

```css
.class {
  width: 50px;
  height: 10%;
  line-height: 2em;
}
```

**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**
