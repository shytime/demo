Atom - Emmet插件的使用详解（HTML/CSS代码自动补全）

## 一、Emmet的安装与介绍

Emmet (前身为 Zen Coding) 是一个能大幅度提高前端开发效率的工具，能够实现 HTML、CSS 的快速编写。

- 官网地址：<http://emmet.io/>
- 官方文档：<http://docs.emmet.io/cheat-sheet/>
- Atom的emmet介绍页面：<https://atom.io/packages/emmet>

### 1，使用Emmet的好处

- 通常大多数的文本编辑器都会允许我们存储和重用一些代码块，我们称之为“片段”。虽然片段能很好地推动我们的生产力，但大多数的实现都有这样一个缺点：我们必须先定义代码片段，并且不能再运行时进行拓展。
- 而 Emmet 把片段这个概念提高到了一个新的层次：我们可以设置 CSS 形式的能够动态被解析的表达式，然后根据输入的缩写来得到相应的内容。Emmet 很成熟的并且非常适用于编写 HTML/XML 和 CSS 代码的前端开发人员，但也可以用于编程语言。

### 2，安装Emmet

Emmet 为大部分流行的编辑器都提供了安装插件，本文演示如何在 Atom 中使用 Emmet 插件。

（1）点击 Atom 的“Preferences”菜单选项（Windows 下是“Settings”菜单选项）

（2）进入到 Install 页面。

（3）搜索“Emmet”包，点击 Install 按钮即可安装。

### 3，简单的使用样例

（1）我们在编辑器中输入如下代码：

```html
ul>li*6
```



（2）接着按下

tab 键，之前的缩写代码就会自动扩展为完整的html 代码片断。

## 二、基本语法

### 1，后代：>

缩写：nav>ul>li

```html
<nav>
    <ul>
        <li></li>
    </ul>
</nav>
```



### 2，兄弟：+

缩写：div+p+bq

```html
<div></div>
<p></p>
<blockquote></blockquote>
```



### 3，上级:^

（1）缩写：div+div>p>span+em^bq

```html
<div></div>
<div>
    <p><span></span><em></em></p>
    <blockquote></blockquote>
</div>
```

（2）缩写：div+div>p>span+em^^bq

```html
<div></div>
<div>
    <p><span></span><em></em></p>
</div>
<blockquote></blockquote>
```



### 4，分组：()

（1）缩写：div>(header>ul>li*2>a)+footer>p

```html
<div>
    <header>
        <ul>
            <li><a href=""></a></li>
            <li><a href=""></a></li>
        </ul>
    </header>
    <footer>
        <p></p>
    </footer>
</div>
```

（2）缩写：(div>dl>(dt+dd)*3)+footer>p

```html
<div>
    <dl>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
        <dt></dt>
        <dd></dd>
    </dl>
</div>
<footer>
    <p></p>
</footer>
```



### 5，乘法：*

缩写：ul>li*5

```html
<ul>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
    <li></li>
</ul>
```



### 6，自增符号：$

（1）缩写：ul>li.item$*5

```html
<ul>
    <li class="item1"></li>
    <li class="item2"></li>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
</ul>
```

（2）缩写：h$[title=item$]{Header $}*3

```html
<h1 title="item1">Header 1</h1>
<h2 title="item2">Header 2</h2>
<h3 title="item3">Header 3</h3>
```

（3）缩写：ul>li.item$$$*5

```html
<ul>
    <li class="item001"></li>
    <li class="item002"></li>
    <li class="item003"></li>
    <li class="item004"></li>
    <li class="item005"></li>
</ul>
```

（4）缩写：ul>li.item$@-*5

```html
<ul>
    <li class="item5"></li>
    <li class="item4"></li>
    <li class="item3"></li>
    <li class="item2"></li>
    <li class="item1"></li>
</ul>
```

（5）缩写：ul>li.item$@3*5

```html
<ul>
    <li class="item3"></li>
    <li class="item4"></li>
    <li class="item5"></li>
    <li class="item6"></li>
    <li class="item7"></li>
</ul>
```



###  7，ID和类属性

（1）缩写：#header

```html
<div id="header"></div>
```

（2）缩写：.title

```html
<div class="title"></div>
```

（3）缩写：form#search.wide

```html
<form id="search" class="wide"></form>
```

（4）缩写：p.class1.class2.class3

```html
<p class="class1 class2 class3"></p
```

### 8，自定义属性

（1）缩写：p[title="Hello world"]

```html
<p title="Hello world"></p>
```

（2）缩写：td[rowspan=2 colspan=3 title]

```html
<td rowspan="2" colspan="3" title=""></td>
```

（3）缩写：[a='value1' b="value2"]

```html
<div a="value1" b="value2"></div>
```



###  9，文本：{}

（1）缩写：a{Click me}

```html
<a href="">Click me</a>
```

（2）缩写：p>{Click }+a{here}+{ to continue}

```html
<p>Click <a href="">here</a> to continue</p>
```

### 10，隐式标签

（1）缩写：.class

```html
<div class="class"></div>
```

（2）缩写：em>.class

```html
<em><span class="class"></span></em>
```

（3）缩写：ul>.class

```html
<ul>    <li class="class"></li></ul>
```

（4）缩写：table>.row>.col

```html
<table>
    <tr class="row">
        <td class="col"></td>
    </tr>
</table>
```



## 三、HTML标签语法

### 1，所有未知的缩写都会转换成标签

缩写：hangge

```html
<hangge></hangge>
```



### 2，基本html标签

（1）缩写：!

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>
   
</body>
</html>
```

（2）缩写：a

```html
<a href=""></a>
```

（3）缩写：a:link

```html
<a href="http://"></a>
```

（4）缩写：a:mail

```html
<a href="mailto:"></a>
```

（5）缩写：abbr

```html
<abbr title=""></abbr>
```

（6）缩写：acronym

```html
<acronym title=""></acronym>
```

（7）缩写：base

```html
`<``base` `href``=``""` `/>`
```

（8）缩写：basefont

```html
<basefont />
```

（9）缩写：br

```html
<br />
```

（10）缩写：frame

```html
<frame />
```

（11）缩写：hr

```html
<hr />
```

（12）缩写：bdo

```html
<bdo dir=""></bdo>
```

（13）缩写：bdo:r

```html
<bdo dir="rtl"></bdo>
```

（14）缩写：bdo:l

```html
<bdo dir="ltr"></bdo>
```

（15）缩写：col

```html
<col />
```

（16）缩写：link

```html
<link rel="stylesheet" href="" />
```

（17）缩写：link:css

```php+HTML
<link rel="stylesheet" href="style.css" />
```

（18）缩写：link:print

```html
<link rel="stylesheet" href="print.css" media="print" />
```

（19）缩写：link:favicon

```html
<link rel="shortcut icon" type="image/x-icon" href="favicon.ico" />
```

（20）缩写：link:touch

```html
<link rel="apple-touch-icon" href="favicon.png" />
```

（21）缩写：link:rss

```html
<link rel="alternate" type="application/rss+xml" title="RSS" href="rss.xml" />
```

（22）缩写：link:atom

```HTML
<link rel="alternate" type="application/atom+xml" title="Atom" href="atom.xml" />
```

（23）缩写：meta

```html
<meta />
```

（24）缩写：meta:utf

```html
<meta http-equiv="Content-Type" content="text/html;charset=UTF-8" />
```

（25）缩写：meta:win

```html
<meta http-equiv="Content-Type" content="text/html;charset=windows-1251" />
```

（26）缩写：meta:vp

```html
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0" />
```

（27）缩写：meta:compat

```html
<meta http-equiv="X-UA-Compatible" content="IE=7" />
```

（28）缩写：style

```html
<style></style>
```

（29）缩写：script



（30）缩写：script:src



（31）缩写：img



（32）缩写：iframe



（33）缩写：embed

```
`<``embed` `src``=``""` `type``=``""` `/>`
```

（34）缩写：object

```
`<``object` `data``=``""` `type``=``""``></``object``>`
```

（35）缩写：param

```
`<``param` `name``=``""` `value``=``""` `/>`
```

（36）缩写：map

```
`<``map` `name``=``""``></``map``>`
```

（37）缩写：area

```
`<``area` `shape``=``""` `coords``=``""` `href``=``""` `alt``=``""` `/>`
```

（38）缩写：area:d

```
`<``area` `shape``=``"default"` `href``=``""` `alt``=``""` `/>`
```

（39）缩写：area:c

```
`<``area` `shape``=``"circle"` `coords``=``""` `href``=``""` `alt``=``""` `/>`
```

（40）缩写：area:r

```
`<``area` `shape``=``"rect"` `coords``=``""` `href``=``""` `alt``=``""` `/>`
```

（41）缩写：area:p

```
`<``area` `shape``=``"poly"` `coords``=``""` `href``=``""` `alt``=``""` `/>`
```

（42）缩写：form

```
`<``form` `action``=``""``></``form``>`
```

（43）缩写：form:get

```
`<``form` `action``=``""` `method``=``"get"``></``form``>`
```

（44）缩写：form:post

```
`<``form` `action``=``""` `method``=``"post"``></``form``>`
```

（45）缩写：label

```
`<``label` `for``=``""``></``label``>`
```

（46）缩写：input

```
`<``input` `type``=``"text"` `/>`
```

（47）缩写：inp

```
`<``input` `type``=``"text"` `name``=``""` `id``=``""` `/>`
```

（48）缩写：input:hidden 

别名：input[type=hidden name]

```
`<``input` `type``=``"hidden"` `name``=``""` `/>`
```

（49）缩写：input:h

别名：input:hidden

```
`<``input` `type``=``"hidden"` `name``=``""` `/>`
```

（50）缩写：input:text, input:t 

别名：inp

```
`<``input` `type``=``"text"` `name``=``""` `id``=``""` `/>`
```

（50）缩写：input:search 

别名：inp[type=search]

```
`<``input` `type``=``"search"` `name``=``""` `id``=``""` `/>`
```

（51）缩写：input:email 

别名：inp[type=email]

```
`<``input` `type``=``"email"` `name``=``""` `id``=``""` `/>`
```

（52）缩写：input:url 

​            别名：inp[type=url]



（53）缩写：input:password 

​            别名：inp[type=password]

```
`<``input` `type``=``"password"` `name``=``""` `id``=``""` `/>`
```

（54）缩写：input:p

​            别名：input:password



（55）缩写：input:datetime 

​            别名：inp[type=datetime]

```
`<``input` `type``=``"datetime"` `name``=``""` `id``=``""` `/>`
```

（56）缩写：input:date 

​            别名：inp[type=date]

```
`<``input` `type``=``"date"` `name``=``""` `id``=``""` `/>`
```

（57）缩写：input:datetime-local 

​            别名：inp[type=datetime-local]

```
`<``input` `type``=``"datetime-local"` `name``=``""` `id``=``""` `/>`
```

（58）缩写：input:month 

​            别名：inp[type=month]

```
`<``input` `type``=``"month"` `name``=``""` `id``=``""` `/>`
```

（59）缩写：input:week

​            别名：inp[type=week]

```
`<``input` `type``=``"week"` `name``=``""` `id``=``""` `/>`
```

（60）缩写：input:time 

​            别名：inp[type=time]

```
`<``input` `type``=``"time"` `name``=``""` `id``=``""` `/>`
```

（61）缩写：input:number

​            别名：inp[type=number]

```
`<``input` `type``=``"number"` `name``=``""` `id``=``""` `/>`
```

（62）缩写：input:color 

​            别名：inp[type=color]

```
`<``input` `type``=``"color"` `name``=``""` `id``=``""` `/>`
```

（63）缩写：input:checkbox 

别名：inp[type=checkbox]

```
`<``input` `type``=``"checkbox"` `name``=``""` `id``=``""` `/>`
```

（64）缩写：input:c 

​            别名：input:checkbox

```
`<``input` `type``=``"checkbox"` `name``=``""` `id``=``""` `/>`
```

（65）缩写：input:radio

​            别名：inp[type=radio]

```
`<``input` `type``=``"radio"` `name``=``""` `id``=``""` `/>`
```

（66）缩写：input:r 

​            别名：input:radio

```
`<``input` `type``=``"radio"` `name``=``""` `id``=``""` `/>`
```

（67）缩写：input:range

​            别名：inp[type=range]

```
`<``input` `type``=``"range"` `name``=``""` `id``=``""` `/>`
```

（68）缩写：input:file 

​            别名：inp[type=file]

```
`<``input` `type``=``"file"` `name``=``""` `id``=``""` `/>`
```

（69）缩写：input:f 

​            别名：input:file

```html
<input type="file" name="" id="" />
```

（70）缩写：input:submit

`<` `type`=``"submit" value``=`""` `/>`

（71）缩写：input:s 

​            别名：input:submit

```
`<``input` `type``=``"submit"` `value``=``""` `/>`
```

（72）缩写：input:image

```
`<``input` `type``=``"image"` `src``=``""` `alt``=``""` `/>`
```

（73）缩写：input:i 

​            别名：input:image



（74）缩写：input:button

```
`<``input` `type``=``"button"` `value``=``""` `/>`
```

（75）缩写：input:b

​            别名：input:button

```
`<``input` `type``=``"button"` `value``=``""` `/>`
```

（76）缩写：isindex

```
`<``isindex` `/>`
```

（77）缩写：input:reset

​            别名：input:button[type=reset]

```
`<``input` `type``=``"reset"` `value``=``""` `/>`
```

（78）缩写：select



（79）缩写：option



（80）缩写：textarea



（81）缩写：menu:context 

​            别名：menu[type=context]> 

```
`<``menu` `type``=``"context"``></``menu``>`
```

（82）缩写：menu:c 

​            别名：menu:context

```
`<``menu` `type``=``"context"``></``menu``>`
```

（83）缩写：menu:toolbar

​            别名：menu[type=toolbar]> 

```
`<``menu` `type``=``"toolbar"``></``menu``>`
```

（84）缩写：menu:t 

​            别名：menu:toolbar

```
`<``menu` `type``=``"toolbar"``></``menu``>`
```

（85）缩写：video

```
`<``video` `src``=``""``></``video``>`
```

（86）缩写：audio

```
`<``audio` `src``=``""``></``audio``>`
```

（87）缩写：html:xml

```
`<``html` `xmlns``=``"http://www.w3.org/1999/xhtml"``></``html``>`
```

（88）缩写：keygen

```
`<``keygen` `/>`
```

（89）缩写：command

```
`<``command` `/>`
```

（90）缩写：bq

​            别名：blockquote

```
`<``blockquote``></``blockquote``>`
```

（91）缩写：acr

别名：acronym

```

```

（92）缩写：fig 

​            别名：figure

```
`<``figure``></``figure``>`
```

（93）缩写：figc 

​            别名：figcaption



（94）缩写：ifr

​            别名：iframe



（95）缩写：emb

​            别名：embed



（96）缩写：obj

​            别名：object



（97）缩写：src

​            别名：source



（98）缩写：cap

​            别名：caption



（99）缩写：colg 

​            别名：colgroup

```html
<colgroup></colgroup>
```

（100）缩写：fst,fset

别名：fieldset

```html
<fieldset></fieldset>
```

（101）缩写：btn

别名：button

```html
<button></button>
```

（102）缩写：btn:b

别名：button[type=button]

```html
<button type="button"></button>
```

（103）缩写：btn:r 

 别名：button[type=reset]

```html
<button type="reset"></button>
```

（104）缩写：btn:s

​              别名：button[type=submit]

```html
<button type="submit"></button>
```



## 四、CSS语法

更多的语法缩写（比如CSS、XSL），可以查看官方的API文档：

http://docs.emmet.io/cheat-sheet/

原文链接：http://www.hangge.com/blog/cache/detail_1537.html