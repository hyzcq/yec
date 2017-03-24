## **HTML编码规范**

### 语法

* 缩进使用soft tab（4个空格）；
* 嵌套的节点应该缩进；
* 在属性上，使用双引号，不要使用单引号；
* 属性名全小写，用中划线做分隔符；
* 不要在自动闭合标签结尾处使用斜线（[HTML5 规范](http://dev.w3.org/html5/spec-author-view/syntax.html#syntax-start-tag) 指出他们是可选的）；
* 不要忽略可选的关闭标签，例：`</li>` 和 `</body>`。

```markdown
<!DOCTYPE html>
<html>
    <head>
        <title>Page title</title>
    </head>
    <body>
        <img src="images/company_logo.png" alt="Company">
        <h1 class="hello-world">Hello, world!</h1>
    </body>
</html>
```

### HTML常用头部标签



### 字符编码

通过声明一个明确的字符编码，让浏览器轻松、快速的确定适合网页内容的渲染方式，通常指定为'UTF-8'。

```
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
    </head>
    ...
</html>
```

### IE兼容模式

用 `<meta>` 标签可以指定页面应该用什么版本的IE来渲染；

如果你想要了解更多，请点击[这里](http://stackoverflow.com/questions/6771258/whats-the-difference-if-meta-http-equiv-x-ua-compatible-content-ie-edge-e)；

```
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    </head>
    ...
</html>
```

### 属性顺序

属性应该按照特定的顺序出现以保证易读性；

* `class`
* `id`
* `name`
* `data-*`
* `src`, `for`, `type`, `href`, `value` , `max-length`, `max`, `min`, `pattern`
* `placeholder`, `title`, `alt`
* `aria-*`, `role`
* `required`, `readonly`, `disabled`

class是为高可复用组件设计的，所以应处在第一位；

id更加具体且应该尽量少使用，所以将它放在第二位。

```
<a class="..." id="..." data-modal="toggle" href="#">Example link</a>

<input class="form-control" type="text">

<img src="..." alt="...">
```

### JS生成标签

在JS文件中生成标签让内容变得更难查找，更难编辑，性能更差。应该尽量避免这种情况的出现。

### 减少标签数量

在编写HTML代码时，需要尽量避免多余的父节点；

很多时候，需要通过迭代和重构来使HTML变得更少。

```
<!-- Not well -->
<span class="avatar">
    <img src="...">
</span>

<!-- Better -->
<img class="avatar" src="...">
```

