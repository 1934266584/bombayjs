## 一个收集前端的错误，行为，pv,性能等的库，不依赖于任何的框架

👏欢迎大家一起共同建设这个库😊😊

##  build
```
npm run build
```

## 功能

* 上报pv uv
* 捕获error
* 上报性能performance
* 上报用户轨迹
* 支持单页面
* hack ajax fetch
* 上报加载的资源
* hack console
* hack onpopstate
* 暴露全局变量__bb
* 埋点 sum avg msg

## 用法

token在bombayjs-admin后台申请

### 方法一
```html
  <script src='../dist/bombay.js'></script>
  <script>
    new Bombay({
      token: 'xxx',
      reportUrl: 'http://127.0.0.1:7002/api/v1/report/web'
    })
  </script>
```

### 方法二
```
npm i bombayjs -S
```

```js
import Bombay from 'bombayjs'
或 var Bombay = require('bombayjs')

new Bombay({
  token: 'xxxx',
  reportUrl: 'http://127.0.0.1:7002/api/v1/report/web'
})
```

## 配置
```js
{
  // 上报地址
  reportUrl: 'http://localhost:10000',
  // 提交参数
  token: '',
  // app版本
  appVersion: '1.0.0',
  // Vue的类
  Vue: '',
  // 环境
  environment: 'production',
  // 脚本延迟上报时间
  outtime: 300,
  // 开启单页面？
  enableSPA: true,
  // 是否自动上报pv
  autoSendPv: true,
  // 是否上报页面性能数据
  isPage: true,
  // 是否上报ajax性能数据
  isAjax: true,
  // 是否上报页面资源数据
  isResource: true,
  // 是否上报错误信息
  isError: true,
  // 是否录屏
  isRecord: true,
  // 是否上报行为
  isBehavior: true,
  ignore: {
    ignoreErrors: [],
    ignoreUrls: [],
    ignorePvs: ['404'],
    // 忽略资源请求
    ignoreResources: [],
    ignoreApis: ['/api/v1/report/web', 'livereload.js?snipver=1', '/sockjs-node/info'],
  },
  behavior: {
    console: ['log', 'error'], // 取值可以是"debug", "info", "warn", "log", "error"
    click: true,
  },
  // 最长上报数据长度
  maxLength: 1000,
  // 当前用户信息
  user: {}
}

```

