1.下载apicloud模板文件[https://github.com/hyzcq/apicloud.git](https://github.com/hyzcq/apicloud.git)

2.在apicloud平台创建app项目，获取项目id

3.将config.xml文件中的id和name更换为新建项目的id和name

![](/assets/apicloud-config.png)

4.文件结构

```
    \|--- index.html    app入口文件

    \|--- css

    \|--- html    页面文件

    \|--- icon   app图标

    \|--- image   项目图片

    \|--- launch   app启动图

    \|---res   公用资源文件

    \|---script   js文件

          \|--- api.js  APICloud 前端框架，[文档地址](https://docs.apicloud.com/Front-end-Framework/framework-dev-guide)

          \|--- common.js   封装通用js方法

          \|--- echo.js   图片懒加载js库，[文档地址](https://github.com/toddmotto/echo)

          \|--- fastclick.min.js   处理移动端点击延迟js库

          \|--- lib.js  引用通用js文件

          \|--- sha1.min.js   sha1加密

          \|--- vue.min.js
```

5.通用方法

* $.ready\(callback\)

  api对象初始化完毕后调用，所有使用到api的方法均需要在方法中调用

  示例代码

  $.ready\(function \(\) {

  ```
    var appId = api.appId;
  ```

  }\)

* toast\({params}\)

  /\*\*

  \* toast提示

  \* @param {String} msg 提示文字信息

  \* @param {Object} toast参数，同api.toast

  \*/

  示例代码

  toast\('网络错误'\)

       toast\({

          msg: '网络错误',

          duration: 2000,

           location: 'bottom'

       }\);

* addEvent\(string, function\)

        监听事件，封装自api.addEventListener方法

        示例代码

        addEvent\('online', function\(value\){

                 console.log\(value\)

        }\)

* sendEvent\(string, {params}\)

        监听事件，封装自api.sendEvent方法

        示例代码

       //html页面a：

        sendEvent\('myEvent', {

                 name:  '张三'

        }\)

      //html页面b：

      addEvent\('myEvent', function\(value\){

                 console.log\(value\)   //b页面将收到 myEvent 事件,输出结果为{name: '张三'}

        }\)

