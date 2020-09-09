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


### 2.
