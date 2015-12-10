#Emmet
**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**

[Emmet](http://docs.emmet.io) (предыдущее название — Zen Coding) — это набор плагинов для различных популярных текстовых редакторов, используемых для скоростного написания HTML и CSS кода.

Для преобразование аббревиатуры в код необходимо нажать клавишу TAB.

#### Doctype

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

#### class и id

div.content

span#search

section#main.user

```html
<div class="content"></div>
<span id="search"></span>
<section id="main" class="user"></section>
```

#### Атрибуты и контент

a.link[href=http://google.com]{google}

img.avatar[src=./default_avatar.jpg][alt=avatar][title=avatar]

```html
<a href="http://google.com" class="link">google</a>
<img src="./default_avatar.jpg" alt="avatar" class="avatar" title="avatar">
```

**[Содержание](https://github.com/EvgeniyPolovniy/fron_end_book)**
