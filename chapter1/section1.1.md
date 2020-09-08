# 前端题目汇总
> 日常问题记录

### 1、typescript 里有哪些 javascript 没有的类型？
#### 1.1 any
声明为 any 的变量可以赋予任意类型的值
#### 1.2 tuple
元组类型用来表示已知元素数量和类型的数组，各元素的类型不必相同，对应位置的类型需要相同。
```
let x: [string, number]
x = ['string', 0]; // 报错
x = [0, 'string']; // 正常
```
#### 1.3  enum





