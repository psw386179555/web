## Set {#Set}

### 基本用法 {#基本用法}

ES6 提供了新的数据结构 Set。它类似于数组，但是成员的值都是唯一的，没有重复的值。

Set 本身是一个构造函数，用来生成 Set 数据结构。

```js
const s = new Set();

[2, 3, 5, 4, 5, 2, 2].forEach(x => s.add(x));

for (let i of s) {
  console.log(i);
}
// 2 3 5 4
```

向 Set 加入值的时候，不会发生类型转换，所以`5`和`"5"`是两个不同的值。Set 内部判断两个值是否不同，使用的算法叫做“Same-value equality”，它类似于精确相等运算符（`===`），主要的区别是`NaN`

等于自身，而精确相等运算符认为`NaN`不等于自身。

```
let set = new Set();
let a = NaN;
let b = NaN;
set.add(a);
set.add(b);
set // Set {NaN}

//另外，两个对象总是不相等的。
let set = new Set();

set.add({});
set.size // 1

set.add({});
set.size // 2
```

### Set 实例的属性和方法 {#Set-实例的属性和方法}

Set 结构的实例有以下属性。

* `Set.prototype.constructor`
  ：构造函数，默认就是
  `Set`
  函数。
* `Set.prototype.size`
  ：返回
  `Set`
  实例的成员总数。

Set 实例的方法分为两大类：操作方法（用于操作数据）和遍历方法（用于遍历成员）。下面先介绍四个操作方法。

* `add(value)`
  ：添加某个值，返回Set结构本身。
* `delete(value)`
  ：删除某个值，返回一个布尔值，表示删除是否成功。
* `has(value)`
  ：返回一个布尔值，表示该值是否为
  `Set`
  的成员。
* `clear()`
  ：清除所有成员，没有返回值。

```
s.add(1).add(2).add(2);
// 注意2被加入了两次

s.size // 2

s.has(1) // true
s.has(2) // true
s.has(3) // false

s.delete(2);
s.has(2) // false

// 对象的写法
const properties = {
  'width': 1,
  'height': 1
};

if (properties[someName]) {
  // do something
}

// Set的写法
const properties = new Set();

properties.add('width');
properties.add('height');

if (properties.has(someName)) {
  // do something
}
```

### 遍历操作 {#遍历操作}

Set 结构的实例有四个遍历方法，可以用于遍历成员。

* `keys()`
  ：返回键名的遍历器
* `values()`
  ：返回键值的遍历器
* `entries()`
  ：返回键值对的遍历器
* `forEach()`
  ：使用回调函数遍历每个成员

需要特别指出的是，`Set`的遍历顺序就是插入顺序。这个特性有时非常有用，比如使用Set保存一个回调函数列表，调用时就能保证按照添加顺序调用。

```js
let set = new Set(['red', 'green', 'blue']);

for (let item of set.keys()) {
  console.log(item);
}
// red
// green
// blue

for (let item of set.values()) {
  console.log(item);
}
// red
// green
// blue

for (let item of set.entries()) {
  console.log(item);
}
// ["red", "red"]
// ["green", "green"]
// ["blue", "blue"]
```



