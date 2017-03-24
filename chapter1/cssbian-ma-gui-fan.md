## **CSS编码规范**

### 语法

* 使用soft tab（4个空格） 。
* 每个属性声明末尾都要加分号 。

### class 命名

* class 名称中只能出现小写字符和破折号（dashe）。破折号应当用于相关 class 的命名（类似于命名空间）（例如，`.btn` 和 `.btn-danger`）。
* 避免过度任意的简写。`.btn` 代表 _button_，但是 `.s` 不能表达任何意思。
* class 名称应当尽可能短，并且意义明确。
* 使用有意义的名称。使用有组织的或目的明确的名称，不要使用表现形式（presentational）的名称。
* 基于最近的父 class 或基本（base） class 作为新 class 的前缀。

```
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

```
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

```
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

    /* 其他 */ 
    opacity: 1;
}
```

### 带前缀的属性

当使用特定厂商的带有前缀的属性时，通过缩进的方式，让每个属性的值在垂直方向对齐，这样便于多行编辑。

```
/* Prefixed properties */
.selector {
  -webkit-box-shadow: 0 1px 2px rgba(0,0,0,.15);
          box-shadow: 0 1px 2px rgba(0,0,0,.15);
}
```

