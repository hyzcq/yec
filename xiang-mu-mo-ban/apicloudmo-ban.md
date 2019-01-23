1.下载apicloud模板文件[https://github.com/hyzcq/apicloud.git](https://github.com/hyzcq/apicloud.git)

2.在apicloud平台创建app项目，获取项目id，创建方法见官方文档[https://docs.apicloud.com/APICloud/junior-develop-guide](https://docs.apicloud.com/APICloud/junior-develop-guide)

3.将config.xml文件中的id和name更换为新建项目的id和name

![](/assets/apicloud-config.png)

4.文件结构

```
    |--- index.html    app入口文件

    |--- css

    |--- html    页面文件

    |--- icon   app图标

    |--- image   项目图片

    |--- launch   app启动图

    |---res   公用资源文件

    |---script   js文件

          |--- api.js  APICloud 前端框架，[文档地址](https://docs.apicloud.com/Front-end-Framework/framework-dev-guide)

          |--- common.js   封装通用js方法

          |--- echo.js   图片懒加载js库，[文档地址](https://github.com/toddmotto/echo)

          |--- fastclick.min.js   处理移动端点击延迟js库

          |--- lib.js  引用通用js文件

          |--- sha1.min.js   sha1加密

          |--- vue.min.js
```

5.通用方法

* $.ready\(callback\)

  api对象初始化完毕后调用，所有使用到api的方法均需要在方法中调用

  示例代码

  ```js
    $.ready(function () {
      var appId = api.appId;
    })
  ```

* toast\({params}\)

  ```js
   /**
   * toast提示
   * @param {String} msg 提示文字信息
   * @param {Object} toast参数，同api.toast
   */
  示例代码

   toast('网络错误')

   toast({
      msg: '网络错误',
      duration: 2000,
      location: 'bottom'
   });
  ```

* addEvent\(string, function\)

  ```js
    监听事件，封装自api.addEventListener方法

    示例代码

    addEvent('online', function(value){
        console.log(value)
    })
  ```

* sendEvent\(string, {params}\)

  ```js
    监听事件，封装自api.sendEvent方法

    示例代码

    //html页面a：
    sendEvent('myEvent', {
        name:  '张三'
    })

    //html页面b：
    addEvent('myEvent', function(value){
        console.log(JSON.stringify(value))   //b页面将收到 myEvent 事件,输出结果为{name: '张三'}
    })
  ```

* openWin\(string, {params}, {option}\)

  ```js
     /**
        * 打开新窗口
        * @param {String} name 打开窗口名及对应url，url与页面文件名对应
        * @param {Object} params 窗口传递页面参数
        * @param {Object} option openWin窗口配置参数,参考api.openWin方法参数
     */
     示例代码
     openWin('page', { id: 1 },  {animation: {type: push}})
  ```

* openFrame\(string, {params}, {option}\)

  ```
    打开新的frame，使用方法及参数同openWin
  ```

* closeWin\(string\)

  ```js
    关闭窗口，string为关闭的窗口名，不传则默认关闭当前窗口
    示例代码
    closeWin()
    closeWin('page1')
  ```

* ajax\({params}\)

  ```js
    /**
     * ajax请求方法，封装api.ajax
     * @param {Object} options            ajax请求参数
     * @param {String} method             请求的类型，默认get
     * @param {String} url                请求地址,可以是相对地址（如/upload），接口地址统一配置，也可以是绝对路径
     * @param {String} timeout            超时时间,单位秒
     * @param {Object} data               请求参数
     * @param {String} dataType           预期服务器返回的数据类型，xml html json ...
     * @param {Object} headers            自定义请求headers
     * @param {Function} success          请求成功后，服务器返回数据[data]
     * @param {Function} error            请求失败
    */

   示例代码
   ajax({
        url: '/upLoad',
        method: 'post',
        dataType: 'json',
        timeout: 10,
        data: {
            values: {
                name: 'person'
             }
         },
         success: function(res){
            console.log(res)  //输出返回数据
         },
         error: function(err){
            console.log(err)  //返回错误信息
         }
    })
  ```



