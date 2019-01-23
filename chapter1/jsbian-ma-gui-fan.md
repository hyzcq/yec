# JS编码规范

### 单行长度

不要超过80，但如果编辑器开启word wrap可以不考虑单行长度。

### 分号

语句结束后需加分号

```js
/* var declaration */
var x = 1;

/* expression statement */
x++;

/* do-while */
do {
    x++;
} while (x < 10);
```

### 换行

换行的地方，行末必须有','或者运算符；

以下几种情况不需要换行：

* 下列关键字后：`else`, `catch`, `finally`

* 代码块'{'前

以下几种情况需要换行：

* 代码块'{'后和'}'前

* 变量赋值后

```js
// not good
var a = {
    b: 1
    , c: 2
};

x = y
    ? 1 : 2;

// good
var a = {
    b: 1,
    c: 2
};

x = y ? 1 : 2;
x = y ?
    1 : 2;

// no need line break with 'else', 'catch', 'finally'
if (condition) {
    ...
} else {
    ...
}

try {
    ...
} catch (e) {
    ...
} finally {
    ...
}

// not good
function test()
{
    ...
}

// good
function test() {
    ...
}

// not good
var a, foo = 7, b,
    c, bar = 8;

// good
var a,
    foo = 7,
    b, c, bar = 8;
```

### 单行注释

双斜线后，必须跟一个空格；

缩进与下一行代码保持一致；

可位于一个代码行的末尾，与代码间隔一个空格。

```js
if (condition) {
    // if you made it here, then all security checks passed
    allowed();
}

var zhangsan = 'zhangsan'; // one space after code
```

### 多行注释

最少三行, '\*'后跟一个空格，具体参照右边的写法；

建议在以下情况下使用：

* 难于理解的代码段

* 可能存在错误的代码段

* 浏览器特殊的HACK代码

* 业务逻辑强相关的代码

```js
/*
 * one space after '*'
 */
var x = 1;
```

### 文档注释

各类标签@param, @method等请参考[usejsdoc](http://usejsdoc.org/)和[JSDoc Guide](http://yuri4ever.github.io/jsdoc/)；

建议在以下情况下使用：

* 常量

* 函数

* 类

```js
/**
 * 注释写明参数类型，是否可选，参数含义
 * @func
 * @desc 一个带参数的函数
 * @param {string} a - 参数a
 * @param {number} b=1 - 参数b默认值为1
 * @param {string} c=1 - 参数c有两种支持的取值
<
/br
>
1—表示x
<
/br
>
2—表示xx
 * @param {object} d - 参数d为一个对象
 * @param {string} d.e - 参数d的e属性
 * @param {string} d.f - 参数d的f属性
 * @param {object[]} g - 参数g为一个对象数组
 * @param {string} g.h - 参数g数组中一项的h属性
 * @param {string} g.i - 参数g数组中一项的i属性
 * @param {string} [j] - 参数j是一个可选参数
 */
function foo(a, b, c, d, g, j) {
    ...
}
```

### 引号

最外层统一使用单引号。

```js
// not good
var x = "test";

// good
var y = 'foo',
    z = '
<
div id="test"
>
<
/div
>
';
```

### 变量命名

* 标准变量采用驼峰式命名（除了对象的属性外，主要是考虑到cgi返回的数据）

* 'ID'在变量名中全大写

* 'URL'在变量名中全大写

* 'Android'在变量名中大写第一个字母

* 'iOS'在变量名中小写第一个，大写后两个字母

* 常量全大写，用下划线连接

* jquery对象必须以'$'开头命名

```js
var thisIsMyName;

var goodID;

var reportURL;

var AndroidVersion;

var iOSVersion;

var MAX_COUNT = 10;

// not good
var body = $('body');

// good
var $body = $('body');
```

### 变量声明

一个函数作用域中所有的变量声明尽量提到函数首部，用一个var声明，不允许出现两个连续的var声明。

```js
function doSomethingWithItems(items) {
    // use one var
    var value = 10,
        result = value + 10,
        i,
        len;

    for (i = 0, len = items.length; i 
<
 len; i++) {
        result += 10;
    }
}
```



