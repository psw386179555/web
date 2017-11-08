# 1.let 和 const

* let用来声明变量。它的用法类似于`var`，但是所声明的变量，只在`let`命令所在的代码块内有效。
* const声明一个只读的常量。一旦声明，常量的值就不能改变。

# 2.变量解构赋值

## 数组解构赋值

```js
let [foo, [[bar], baz]] = [1, [[2], 3]];
foo // 1
bar // 2
baz // 3

let [ , , third] = ["foo", "bar", "baz"];
third // "baz"

let [x, , y] = [1, 2, 3];
x // 1
y // 3

let [head, ...tail] = [1, 2, 3, 4];
head // 1
tail // [2, 3, 4]

let [x, y, ...z] = ['a'];
x // "a"
y // undefined
z // []
```

## 对象的解构赋值

```js
let { bar, foo } = { foo: "aaa", bar: "bbb" };
foo // "aaa"
bar // "bbb"

let { baz } = { foo: "aaa", bar: "bbb" };
baz // undefined

let { foo: baz } = { foo: 'aaa', bar: 'bbb' };
baz // "aaa"

let obj = { first: 'hello', last: 'world' };
let { first: f, last: l } = obj;
f // 'hello'
l // 'world'
```

## 字符串的解构赋值

```js
const [a, b, c, d, e] = 'hello';
a // "h"
b // "e"
c // "l"
d // "l"
e // "o"


let {length : len} = 'hello';
len // 5
```

## 数组和布尔解构赋值

```js
let {toString: s} = 123;
s === Number.prototype.toString // true

let {toString: s} = true;
s === Boolean.prototype.toString // true
```

## 用途

**（1）交换变量的值**

```js
let x = 1;
let y = 2;

[x, y] = [y, x];
```

**（2）从函数返回多个值**

```js
function example() {
  return [1, 2, 3];
}
let [a, b, c] = example();

// 返回一个对象

function example() {
  return {
    foo: 1,
    bar: 2
  };
}
let { foo, bar } = example();
```

**（3）函数参数的定义**

```js
// 参数是一组有次序的值
function f([x, y, z]) { ... }
f([1, 2, 3]);

// 参数是一组无次序的值
function f({x, y, z}) { ... }
f({z: 3, y: 2, x: 1});
```

**（4）提取JSON数据**

```js
let jsonData = {
  id: 42,
  status: "OK",
  data: [867, 5309]
};

let { id, status, data: number } = jsonData;

console.log(id, status, number);
// 42, "OK", [867, 5309]
```

**（5）函数参数的默认值**

```js
jQuery.ajax = function (url, {
  async = true,
  beforeSend = function () {},
  cache = true,
  complete = function () {},
  crossDomain = false,
  global = true,
  // ... more config
}) {
  // ... do stuff
};
```

**（6）遍历Map结构**

```js
const map = new Map();
map.set('first', 'hello');
map.set('second', 'world');

for (let [key, value] of map) {
  console.log(key + " is " + value);
}
```

**（7）输入模块的指定方法**

```js
const { SourceMapConsumer, SourceNode } = require("source-map");
```

# 3.字符串拓展

## 字符串的遍历器接口 {#字符串的遍历器接口}

```js
for (let codePoint of 'foo') {
  console.log(codePoint)
}
// "f"
// "o"
// "o"
```

## includes\(\), startsWith\(\), endsWith\(\) {#includes-startsWith-endsWith}

* **includes\(\)**：返回布尔值，表示是否找到了参数字符串。
* **startsWith\(\)**：返回布尔值，表示参数字符串是否在原字符串的头部。
* **endsWith\(\)**：返回布尔值，表示参数字符串是否在原字符串的尾部。

```js
let s = 'Hello world!';

s.startsWith('Hello') // true
s.endsWith('!') // true
s.includes('o') // true


//这三个方法都支持第二个参数，表示开始搜索的位置。

let s = 'Hello world!';

s.startsWith('world', 6) // true
s.endsWith('Hello', 5) // true
s.includes('Hello', 6) // false
```

## 模板字符串 {#模板字符串}

* 模板字符串中嵌入变量，需要将变量名写在`${}`之中。
* 大括号内部可以放入任意的JavaScript表达式，可以进行运算，以及引用对象属性。

```js
$('#result').append(`
  There are <b>${basket.count}</b> items
   in your basket, <em>${basket.onSale}</em>
  are on sale!
`);
```

# 4.函数的扩展

## 函数参数的默认值

```js
function log(x, y = 'World') {
  console.log(x, y);
}

log('Hello') // Hello World
log('Hello', 'China') // Hello China
log('Hello', '') // Hello
```

## rest 参数 {#rest-参数}

ES6 引入 rest 参数（形式为`...变量名`），用于获取函数的多余参数，这样就不需要使用

`arguments`对象了。rest 参数搭配的变量是一个数组，该变量将多余的参数放入数组中。

```js
function add(...values) {
  let sum = 0;

  for (var val of values) {
    sum += val;
  }

  return sum;
}

add(2, 5, 3) // 10

//上面代码的add函数是一个求和函数，利用 rest 参数，可以向该函数传入任意数目的参数。
```

## name 属性 {#name-属性}

函数的`name`属性，返回该函数的函数名。如果将一个匿名函数赋值给一个变量，ES5 的

`name`属性，会返回空字符串，而 ES6 的`name`属性会返回实际的函数名。

```js
var f = function () {};

// ES5
f.name // ""

// ES6
f.name // "f"
```

## 箭头函数 {#箭头函数}

ES6 允许使用“箭头”（`=>`）定义函数。

```js
var f = () => 5;
// 等同于
var f = function () { return 5 };

var sum = (num1, num2) => num1 + num2;
// 等同于
var sum = function(num1, num2) {
  return num1 + num2;
};
```

箭头函数可以与变量解构结合使用。

