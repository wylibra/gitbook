# 随手记
> 没有整理文档，随手记录遇到的各种问题～

### 1.如何在vue main.js里面用this.$message('消息')？（2020.09.09）
- 方式1

在main.js里面是没办法用this.$message的这种方法的，this这时候指向的是window，你又没给window注册这个方法
单独引入
```
import  { Message } from 'element-ui'
引用：Message(options)
带状态图标的引用：Message.success(options)
手动关闭：Message.closeAll()
```
- 方式2
```
Vue.prototype.$message('success')
```


### 2.axios添加请求拦截器

```
import axios from 'axios';

const service = axios.create({
  baseURL: host, // 代理
  timeout: 15000 // 请求超时时间
})

// 添加请求拦截器
service.interceptors.request.use(
  function (config) {
    console.log(userInfo);

    //统一参数 post请求
    let userInfo = localStorage.getItem("userInfo") ? JSON.parse(localStorage.getItem("userInfo")) : '';
    if (config.data) {
      config.data.createId = userInfo.userId;
    }
    //统一参数 get请求
    if (config.params) {
      config.params.createId = userInfo.userId;
    }
    // 统一参数 headers
    if (config) {
      if (!path.includes(config.url)) {
        const token = localStorage.getItem('token')
        const baseSet = {
          'Authorization': 'Bearer ' + token
        }
        config.headers = Object.assign({}, baseSet, config.headers)
      }
    }
    return config;
  },
  function (error) {
    // 对请求错误做些什么
    return Promise.reject(error);
  }
);
```
### 3.obj.fn?.() 是什么意思？
判断是否存在，存在则执行函数
```
function func(){ console.log('ceshi'); }
var obj ={
  fn: func
}
function test(){
  obj.fn?.();
}
test() // VM1579:1 ceshi
```

