# 汇总
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




