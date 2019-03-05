## 1 前言

默认开发者具有一定的前端开发经验，会能够运用html、css编写普通页面，并且有一定的js编程运用能力。如果不具备请先学习前端基础课程。

  


## 2 开始

#### 2.1 开始前的环境、以及工具准备 

1. 你需要拥有一个小程序帐号，通过这个帐号你就可以管理你的小程序。账号申请，查看小程序APPID，以及小程序的各项设置的具体操作方法  [前往查看](https://developers.weixin.qq.com/miniprogram/dev/)。

2. 安装开发者工具，小程序的开发需要微信开发者工具。前往下载 [前往查看](https://developers.weixin.qq.com/miniprogram/dev/devtools/download.html?t=19021321)。

  


#### 2.2 小程序代码结构，以及能力

1. 小程序的代码构成 [前往查看](https://developers.weixin.qq.com/miniprogram/dev/quickstart/basic/file.html#json-%E9%85%8D%E7%BD%AE)

2. 小程序能力  [前往查看](https://developers.weixin.qq.com/miniprogram/dev/quickstart/basic/framework.html#%E5%B0%8F%E7%A8%8B%E5%BA%8F%E7%9A%84%E5%90%AF%E5%8A%A8)

3. 发布前准备，以及上线 [前往查看](https://developers.weixin.qq.com/miniprogram/dev/quickstart/basic/role.html#%E7%94%A8%E6%88%B7%E8%BA%AB%E4%BB%BD)

  






## 3 小程序基础框架

小程序开发框架的目标是通过尽可能简单、高效的方式让开发者可以在微信中开发具有原生 APP 体验的服务。

框架提供了自己的视图层描述语言 WXML 和 WXSS，以及基于 JavaScript 的逻辑层框架，并在视图层与逻辑层间提供了数据传输和事件系统，让开发者能够专注于数据与逻辑。

小程序核心是一个数据绑定系统。开发者只需要关心业务数据的变化。通过数据改变来驱动页面的响应等。

对于小程序的页面，框架提供了wxml、以及wxss。wxml文件只能包括小程序特有的组件标签。wxss实际上就是css只是修改了文件的后缀罢了。

具体框架官方文档 [前往查看](https://developers.weixin.qq.com/miniprogram/dev/framework/MINA.html)

  


对于框架开发者必需了解的方面  


1. 掌握小程序整体的目录结构

2. 掌握小程序全局配置、页面配置 [前往查看](https://developers.weixin.qq.com/miniprogram/dev/framework/config.html#%E5%85%A8%E5%B1%80%E9%85%8D%E7%BD%AE)

3. 掌握逻辑层、视图层。其中逻辑层需要了解如何注册程序，如何注册页面。视图层需要了解数据渲染、事件绑定，引用文件等。[前往查看](https://developers.weixin.qq.com/miniprogram/dev/framework/app-service/app.html)

4. 初步了解小程序的基础能力、硬件能力，以及开放能力。（大概知道这些能力的概念以后处理业务逻辑的时候能够用到）[前往查看](https://developers.weixin.qq.com/miniprogram/dev/framework/ability/network.html)

5. 了解可用性,大概知道环境差异以及如何debug [前往查看](https://developers.weixin.qq.com/miniprogram/dev/framework/usability/debug.html)

  


**小程序官方开发指南 **[**前往查看**](https://developers.weixin.qq.com/ebook?action=get_post_info&docid=0008aeea9a8978ab0086a685851c0a)  


**小程序开发者社区 **[**前往查看**](https://developers.weixin.qq.com/)（遇到不明白的问题可以上社区搜索提问）

  




## 4 小程序框架

区别于小程序基础框架，通过前端打包工具进行编译最终生成符合小程序规范的代码的工具。通常这些框架能够使开发者编写小程序代码变得更方便快捷。  


  


由于使用这些框架编写的代码是不能直接运行，需要开发者进行编译，因此需要开发者安装编译环境。通常对于前端代码都是通过nodejs 进行编译处理的。安装好nodejs后需要开发者根据框架的需求通过命令行工具创建该框架的小程序项目。（需要会使用npm/yarn安装依赖以及运行命令）

  


目前比较成熟且常用的小程序框架有 wepy、 mpvue，这两种框架都类似于前端热门框架vue.js 的风格。因此学习过vue.js的开发者再来使用这两个框架将很容易上手。

  


#### 4.1 mpvue

mpvue 继承自 Vue.js，其技术规范和语法特点与 Vue.js 保持一致。

  


vue.js文档 [前往查看](https://cn.vuejs.org/)

mpvue文档 [前往查看](http://mpvue.com/)

  


通过 Vue.js 命令行工具 vue-cli，快速创建和启动一个带热重载、保存时静态检查、内置代码构建功能的小程序项目：

```
# 全局安装 vue-cli
$ npm install --global vue-cli
# 创建一个基于 mpvue-quickstart 模板的新项目
$ vue init mpvue/mpvue-quickstart my-project
# 安装依赖
$ cd my-project
$ npm install# 启动构建
$ npm run dev
```

mpvue官方快速上手文档 [前往查看](http://mpvue.com/mpvue/quickstart/)  


  


需要注意事项：

1.由于小程序的环境非正常的浏览器环境。因此需要了解一些无法在小程序里实现的一些vue的语法，以及函数，具体情况 [前往查看](http://mpvue.com/mpvue/#_6)。  


2.新增的页面需要重新 npm run dev 来进行编译

  




#### 4.2 wepy



WePY 框架在开发过程中参考了 Vue 等现有框架的一些语法风格和功能特性，对原生小程序的开发模式进行了再次封装，更贴近于 MVVM 架构模式, 并支持ES6/7的一些新特性。

  


wepy文档 [前往查看](https://tencent.github.io/wepy/index.html)

  


快速创建wepy项目：

```
npm install wepy-cli -g
wepy new myproject 
# 1.7.0之后的版本使用 wepy init standard myproject 初始化项目，使用 wepy list 查看项目模板
cd myproject
npm  install
wepy build --watch
```

项目目录

```
├── dist                   小程序运行代码目录（该目录由WePY的build指令自动编译生成，请不要直接修改该目录下的文件）
├── node_modules           
├── src                    代码编写的目录（该目录为使用WePY后的开发目录）
|   ├── components         WePY组件目录（组件不属于完整页面，仅供完整页面或其他组件引用）
|   |   ├── com_a.wpy      可复用的WePY组件a
|   |   └── com_b.wpy      可复用的WePY组件b
|   ├── pages              WePY页面目录（属于完整页面）
|   |   ├── index.wpy      index页面（经build后，会在dist目录下的pages目录生成index.js、index.json、index.wxml和index.wxss文件）
|   |   └── other.wpy      other页面（经build后，会在dist目录下的pages目录生成other.js、other.json、other.wxml和other.wxss文件）
|   └── app.wpy            小程序配置项（全局数据、样式、声明钩子等；经build后，会在dist目录下生成app.js、app.json和app.wxss文件）
└── package.json           项目的package配置
```

类vue开发风格，与mpvue相比更接近与原生的小程序代码风格。

  


使用wepy时，小程序编辑器选项需注意：

es6: 对应关闭ES6转ES5选项，关闭。 重要：未关闭会运行报错。

postcss: 对应关闭上传代码时样式自动补全选项，关闭。 重要：某些情况下漏掉此项也会运行报错。

minified: 对应关闭代码压缩上传选项，关闭。重要：开启后，会导致真机computed, props.sync 等等属性失效。（注：压缩功能可使用WePY提供的build指令代替，详见后文相关介绍以及Demo项目根目录中的wepy.config.js和package.json文件。）

urlCheck: 对应不检查安全域名选项，开启。 如果已配置好安全域名则建议关闭。

  


wepy使用脏数据检查对setData进行封装，在函数运行周期结束时执行脏数据检查，一来可以不用关心页面多次setData是否会有性能上的问题，二来可以更加简洁去修改数据实现绑定，不用重复去写setData方法。代码如下：

```
this.title = 'this is title';
```

  


需注意的是，在异步函数中更新数据的时候，必须手动调用$apply方法，才会触发脏数据检查流程的运行。如：

```
setTimeout(() =
>
 {
    this.title = 'this is title';
    this.$apply(); //异步函数里需要调用$apply()方法来更新数据
}, 3000);
```



新增的页面或者文件时需要重新命令行运行npm run dev编译

