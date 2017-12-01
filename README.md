# weapp-doc
小程序开发笔记

## 代码及文件结构

  components/

  pages/

      index/components/

      index/index.json

      index/index.wxml

      index/index.wxss

      index/index.js

  app.js

  app.json

  app.wxss

## 如何像前端H5一样编写小程序代码（脚手架）

### 1.格式转化

  wxml html

  wxss scss/css

  <image>   <img>

### 2.像js/html/css一样编译

### 3.路径转换、静态资源cdn上传

### 4.格式转化

  html wxml

  scss/css  wxss

  <img>  <image>

## 其它成熟脚手架

 WePY (类Vue.js风格、支持npm包、支持ES6/7(async/await))

 labrador （支持npm包、支持ES6/7(async/await)、数据流（redux)、强类型检查（flow.js))


## UI框架

 weui-wxss （同微信原生视觉体验一致的基础样式库）

 Wa-UI （针对微信小程序整合的一套UI库）

## 小程序服务端支持云部署（nodejs/php)

## 小程序开发

 生命周期 (类react)

 数据流 （类react)

 登录授权

 权限拦截

 dom与H5区别（div和view）

 常用api（网络请求、本地存储、媒体播放、交互）

 页面切换的问题（渲染数据、页面对象的数据是否销毁）

 开发者工具调试（类chrome debug)
# 踩坑

 1.当页面有新增或删除，需要重启开发者工具

 2.scroll-view组件不支持非亲子结点的滚动定位。

 3.data数据中存在undefined或null的值时会报错

 4.页面退出时，dom(data数据相关)会销毁，但页面对象数据不销毁，且定时器、websocket仍会继续运行。运行时可能会报错（nodeId of undefined)

 5.页面隐藏时，页面data数据不可读取（不可写），否则报错

 6.backgroundAudioManager播放音频，其它如title等字段必填，否则无法播放（与它文档不符）

 7.backgroundAudioManager事件不可重复监听，同一事件只能覆盖监听

 8.backgroundAudioManager加载音频失败均报错误码10002（网络错误）

 9.backgroundAudioManager播放不支持的音频时，系统会弹窗提示不支持，该弹窗不可定制取消。

 10.只有backgroundAudioManager支持背景播放且播放能力更强，其它音频api不支持（文档已有更新强调这一点）

 11.request合法域名只有一个，若需要日志打点需要解决域名问题（可使用wx.getImageInfo解决）

 12.小程序内嵌H5不支持普通二维码长按识别、样式会错乱后再恢复

 13.小程序样式不支持级联定义（现实开发中发现可以，但不确定后续版本是否支持）

 14. 1rpx = 0.5px = 1物理像素. 750px设计图，按设计图比例开发，单位使用rpx

 15. slider 不支持定义拖动圆点样式，需要自己实现slider组件。

 16. dom查询有组件限制，使用时要区分dom是否在组件内

 17. 使用text标签要注意， 它有默认样式，文字前面不加空格会显示不出来内容。

 18. 基础库版本问题（语法支持程度、微信api支持程度）

 19.开发者工具中AppData看不到组件内部数据

 20.组件样式不能继承父组件样式，不能复用。

 21.自定义组件会额外创建一个自定义标签，且根结点样式不能写在组件内，需定义在父组件内部，且不支持style,只能通过class。

 22.图片样式要指定高宽和mode，否则会超出容器。且有默认样式（320*240）

 23.非用户触发后进行的音频播放器初始化，在android上会报错，但不影响播放。

 24.
