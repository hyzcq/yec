html,h1,h2,h3,h4,h5,h6,div,body,dl,dd,ul,ol,h1,h2,h3,h4,h5,h6,p,form,input,textarea,button,th,td{

```
margin:0;

padding:0;

font-family: "Microsoft YaHei","Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB", "\5FAE\8F6F\96C5\9ED1", Arial, sans-serif;
```

}

img,iframe{border:0;}

table{border-collapse:collapse;border-spacing:0;table-layout:fixed}

ol,ul{list-style:none outside none}

em,strong,i{font-style:normal;font-weight:bold}

/\*input 去掉chrome选中input时的外边框\*/

input,a,button{outline:none;border:0;text-decoration:none;}

html,body{

```
-webkit-text-size-adjust: 100%;

-webkit-user-select: none;

user-select: none;

-webkit-touch-callout: none;

-webkit-overflow-scrolling : touch;

max-width: 750px;

margin: 0 auto;

overflow-x: hidden;
```

}

/\* 定义rem\*/

html{

```
font-size: calc(100vw / 7.5);
```

}

@media screen and \(max-width: 320px\) {

```
html {

    font-size: 42.6667px;

}
```

}

@media screen and \(min-width: 540px\) {

```
html {

    font-size: 108px;

}
```

}

body,div,ul,li,a,p,h4{

```
font-size: .28rem;
```

}

\*{

```
-webkit-touch-callout:none;

-moz-touch-callout:none;

-ms-touch-callout:none;

touch-callout:none;

box-sizing: border-box;
```

}

li{

```
list-style: none;
```

}

a{

```
text-decoration: none;

display: inline-block;
```

}

.pull-left{

```
float: left!important;
```

}

.pull-right{

```
float: right!important;
```

}

.clear:after{

```
content: '';

display: block;

clear: both;
```

}

.text-ellipsis{

```
overflow: hidden;

text-overflow: ellipsis;

white-space: nowrap;
```

}

.text-ellipsis2{

```
overflow: hidden;

text-overflow: ellipsis;

display: -webkit-box;

-webkit-line-clamp: 2;

-webkit-box-orient: vertical;
```

}

.text-ellipsis3{

```
overflow: hidden;

text-overflow: ellipsis;

display: -webkit-box;

-webkit-line-clamp: 3;

-webkit-box-orient: vertical;
```

}

/\* 隐藏, 通常用来与 JS 配合 \*/

.hide {

```
display: none;
```

}

/\* 设置文本对齐方式\*/

.text-left {

```
text-align: left!important;
```

}

.text-center {

```
text-align: center!important;
```

}

.text-right {

```
text-align: right!important;
```

}

.small {

```
font-size: .8em;
```

}

.strong {

```
font-size: 1.2em;
```

}

