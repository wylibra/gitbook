# 汇总
> 日常问题记录

### 1、typescript 里有哪些 javascript 没有的类型？
`javascript`
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
枚举类型用于定义值集合
```
enum Color {
  Red,
  Green,
  Blue,
}
let c: Color = Color.Blue;
console.log(c); // 2
```
#### 1.4 void
标识方法返回值的类型，表示方法没有返回值
```
function hello(): void {}
```
#### 1.5 never
never是其他类型（包括null 和 undefined）的子类型，是不会发生的类型。
```
// 返回 never 的函数终点不可达
function error(message: string): never {
  throw new Error(message);
}

// 推断的返回类型是 never
function fail() {
  return error('failed');
}

// 返回 never 的函数终点不可达
function infiniteLoop(): never {
  while(true) {}
}
```
#### 1.6 unknown
未知类型，一般在使用到时手动转型
上述都是ts的基本类型
#### 1.7 union
联合类型，多种类型之一
```
string | number; // string 或number
```
#### 1.8 intersection
交叉类型，多种类型合并
```
{a: string;} & {b: number;}
```
#### 1.9 Generics
泛型
```
interface Backpack<T> {
  add: (obj: T) => void;
  get: () => T;
}
```

### 2、BFC 是什么？触发 BFC 的条件是什么？有哪些应用场景？
`css`
#### 1.概念
BFC（Box Formatting context）:Box是css布局的对象和基础单位，BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。

块级格式化上下文布局规则
- 内部的BOX会在垂直方向一个接一个的放置；
- 属于同一个BFC的两个相邻Box的margin会重叠；不同BFC就不会；
- 是页面上一个隔离的独立容器，里面的元素不会影响到外面的元素；反之亦然；
- BFC的区域不会和float box重叠；
- 计算BFC的高度，浮动元素也参与计算；

#### 2.触发条件
- 根元素( <html> )
- 浮动元素( float属性不为none )
- 绝对定位元素( position为absolute或fixed )
- overflow不为visible的块元素
- 行内块元素( display为inline-block )
- 表格单元格、表格标题( table-cell，table-caption )
- 弹性元素( flex，inline-flex )

#### 3.应用场景


### 3、说说浏览器渲染流程，分层之后在什么时候合成，什么是重排、重绘，怎样渲染？
`css`


### 4、有 1000 个dom，需要更新其中的 100 个，如何操作才能减少 dom 的操作？
`javascript`




