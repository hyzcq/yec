## CSS编码规范

### 语法

* 使用soft tab（4个空格） 。
* 每个属性声明末尾都要加分号 。

* 声明块的右花括号应当单独成行。

* 每条声明语句的 `:` 后应该插入一个空格。

* 为了获得更准确的错误报告，每条声明都应该独占一行。

```css
/* Bad CSS */
.selector, .selector-secondary, .selector[type=text] {
  padding:15px;
  margin:0px 0px 15px;
  background-color:rgba(0, 0, 0, 0.5);
  box-shadow:0px 1px 2px #CCC,inset 0 1px 0 #FFFFFF
}

/* Good CSS */
.selector,
.selector-secondary,
.selector[type="text"] {
  padding: 15px;
  margin-bottom: 15px;
  background-color: rgba(0,0,0,.5);
  box-shadow: 0 1px 2px #ccc, inset 0 1px 0 #fff;
}
```

### reset.css

重置浏览器默认样式常用reset.css

```css
html,h1,h2,h3,h4,h5,h6,div,body,dl,dd,ul,ol,h1,h2,h3,h4,h5,h6,p,form,input,textarea,button,th,td{
    margin:0;
    padding:0;
    font-family: "Microsoft YaHei","Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB", "\5FAE\8F6F\96C5\9ED1", Arial, sans-serif;
}
img,iframe{border:0;}
table{border-collapse:collapse;border-spacing:0;table-layout:fixed}
ol,ul{list-style:none outside none}
em,strong,i{font-style:normal;font-weight:bold}

/*input 去掉chrome选中input时的外边框*/
input,a,button{outline:none;border:0;text-decoration:none;}
html,body{
    -webkit-text-size-adjust: 100%;
    -webkit-user-select: none;
    user-select: none;
    -webkit-touch-callout: none;
    -webkit-overflow-scrolling : touch;
    max-width: 750px;
    margin: 0 auto;
    overflow-x: hidden;
}
/*移动端设置基础rem*/
html{
    font-size: calc(100vw / 7.5);
}
@media screen and (max-width: 320px) {
    html {
        font-size: 42.6667px;
    }
}
@media screen and (min-width: 540px) {
    html {
        font-size: 108px;
    }
}
```

### class 命名

* class 名称中只能出现小写字符和破折号“-”（dashe）。破折号应当用于相关 class 的命名（类似于命名空间）（例如，`.btn` 和 `.btn-danger`）。
* 避免过度任意的简写。`.btn` 代表 _button_，但是 `.s` 不能表达任何意思。
* class 名称应当尽可能短，并且意义明确。
* 使用有意义的名称。使用有组织的或目的明确的名称，不要使用表现形式（presentational）的名称。
* 基于最近的父 class 或基本（base） class 作为新 class 的前缀。

```css
/* Bad example */
.t { ... }
.red { ... }
.header { ... }

/* Good example */
.tweet { ... }
.tweet-header { ... }
```

### 代码组织

* 以组件为单位组织代码段。
* 制定一致的注释规范，确保代码能够注释良好并且易于他人理解。 。
* 使用一致的空白符将代码分隔成块，这样利于扫描较大的文档。
* 如果使用了多个 CSS 文件，将其按照组件而非页面的形式分拆，因为页面会被重组，而组件只会被移动。

```css
/*
 * Component section heading
 */

.element { ... }


/*
 * Component section heading
 * 不同组件css样式用空白符或注释分隔代码
 * Sometimes you need to include optional context for the entire component. Do that up here if it's important enough.
 */

.element { ... }

/* Contextual sub-component or modifer */
.element-heading { ... }
```

### 属性声明顺序

相关的属性声明按右边的顺序做分组处理，组之间需要有一个空行。

```css
.declaration-order {
    /* Positioning */ 
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    z-index: 100;

    /* Box-model */ 
    display: block;
    float: right;
    border: 1px solid #e5e5e5;
    border-radius: 3px;
    width: 100px;
    height: 100px;

    /* Typography */ 
    font: normal 13px "Helvetica Neue", sans-serif;
    line-height: 1.5;
    text-align: center;

    /* Visual */ 
    color: #333;
    background-color: #f5f5f5;

    /* others */ 
    opacity: 1;
}
```

### 带前缀的属性

当使用特定厂商的带有前缀的属性时，通过缩进的方式，让每个属性的值在垂直方向对齐，这样便于多行编辑。

```css
/* Prefixed properties */
.selector {
  -webkit-box-shadow: 0 1px 2px rgba(0,0,0,.15);
          box-shadow: 0 1px 2px rgba(0,0,0,.15);
}
```

### 选择器

* 对于通用元素使用 class ，这样利于渲染性能的优化。
* 对于经常出现的组件，避免使用属性选择器（例如，`[class^="..."]`）。浏览器的性能会受到这些因素的影响。
* 选择器要尽可能短，并且尽量限制组成选择器的元素个数，建议不要超过 3 。
* **只有**在必要的时候才将 class 限制在最近的父元素内（也就是后代选择器）（例如，不使用带前缀的 class 时 -- 前缀类似于命名空间）。

扩展阅读：

* [Scope CSS classes with prefixes](http://markdotto.com/2012/02/16/scope-css-classes-with-prefixes/)
* [Stop the cascade](http://markdotto.com/2012/03/02/stop-the-cascade/)

```css
/* Bad example */
span { ... }
.page-container #stream .stream-item .tweet .tweet-header .username { ... }
.avatar { ... }

/* Good example */
.avatar { ... }
.tweet-header .username { ... }
.tweet .avatar { ... }
```

### 常用的CSS布局

#### [http://nec.netease.com/library/category/\#grid](http://nec.netease.com/library/category/#grid)

#### ![](/assets/import.png)

### ![](/assets/import2.png)

### 常用的CSS命名规则

**\(1\)页面结构**

容器: container

页头：header

内容：content\/container

页面主体：main

页尾：footer

导航：nav

侧栏：sidebar

栏目：column

页面外围控制整体佈局宽度：wrapper

左右中：left right center

**\(2\)导航**

导航：nav

主导航：mainnav

子导航：subnav

顶导航：topnav

边导航：sidebar

左导航：leftsidebar

右导航：rightsidebar

菜单：menu

子菜单：submenu

标题: title

摘要: summary

**\(3\)功能**

标志：logo

广告：banner

登陆：login

登录条：loginbar

注册：register

搜索：search

功能区：shop

标题：title

加入：joinus

状态：status

按钮：btn

滚动：scroll

标籤页：tab

文章列表：list

提示信息：msg

当前的: current

小技巧：tips

图标: icon

注释：note

指南：guild

服务：service

热点：hot

新闻：news

下载：download

投票：vote

合作伙伴：partner

友情链接：link

版权：copyright

