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


set = new Set([1, 4, 9]);
set.forEach((value, key) => console.log(key + ' : ' + value))
```

## WeakSet {#WeakSet}

### 含义 {#含义}

WeakSet 结构与 Set 类似，也是不重复的值的集合。但是，它与 Set 有两个区别。

首先，WeakSet 的成员只能是对象，而不能是其他类型的值。

## Map {#Map}

### 含义和基本用法 {#含义和基本用法}

JavaScript 的对象（Object），本质上是键值对的集合（Hash 结构），但是传统上只能用字符串当作键。这给它的使用带来了很大的限制。

上面代码原意是将一个 DOM 节点作为对象`data`的键，但是由于对象只接受字符串作为键名，所以`element`被自动转为字符串`[object HTMLDivElement]`。

为了解决这个问题，**ES6 提供了 Map 数据结构。它类似于对象，也是键值对的集合，但是“键”的范围不限于字符串，各种类型的值（包括对象）都可以当作键。**也就是说，Object 结构提供了“字符串—值”的对应，Map结构提供了“值—值”的对应，是一种更完善的 Hash 结构实现。如果你需要“键值对”的数据结构，Map 比 Object 更合适。

### 实例的属性和操作方法 {#实例的属性和操作方法}

Map 结构的实例有以下属性和操作方法。

**（1）size属性**

`size`属性返回 Map 结构的成员总数。

**（2）set\(key, value\)**

`set`方法设置键名`key`对应的键值为`value`，然后返回整个 Map 结构。如果`key`已经有值，则键值会被更新，否则就新生成该键。`set`**方法返回的是当前的**`Map`**对象，因此可以采用链式写法。**

**（3）get\(key\)**

`get`方法读取`key`对应的键值，如果找不到`key`，返回`undefined`。

**（4）has\(key\)**

`has`方法返回一个布尔值，表示某个键是否在当前 Map 对象之中。

**（5）delete\(key\)**

`delete`方法删除某个键，返回`true`。如果删除失败，返回`false`。

**（6）clear\(\)**

`clear`方法清除所有成员，没有返回值。

### 遍历方法 {#遍历方法}

Map 结构原生提供三个遍历器生成函数和一个遍历方法。

* `keys()`
  ：返回键名的遍历器。
* `values()`
  ：返回键值的遍历器。
* `entries()`
  ：返回所有成员的遍历器。
* `forEach()`
  ：遍历 Map 的所有成员。

需要特别注意的是，**Map 的遍历顺序就是插入顺序**。

```js
const map = new Map([
  ['F', 'no'],
  ['T',  'yes'],
]);

for (let key of map.keys()) {
  console.log(key);
}
// "F"
// "T"

for (let value of map.values()) {
  console.log(value);
}
// "no"
// "yes"

for (let item of map.entries()) {
  console.log(item[0], item[1]);
}
// "F" "no"
// "T" "yes"

// 或者
for (let [key, value] of map.entries()) {
  console.log(key, value);
}
// "F" "no"
// "T" "yes"

// 等同于使用map.entries()
for (let [key, value] of map) {
  console.log(key, value);
}
// "F" "no"
// "T" "yes"
```

## WeakMap {#WeakMap}

### 含义 {#含义}

`WeakMap`结构与`Map`结构类似，也是用于生成键值对的集合。

首先，`WeakMap`只接受对象作为键名（`null`除外），不接受其他类型的值作为键名。

其次，`WeakMap`的键名所指向的对象，不计入垃圾回收机制。

