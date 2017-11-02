# 1.基本逻辑

* ## if

* _if 语句_

 只有当指定条件为 true 时，使用该语句来执行代码

* _if...else 语句_

 当条件为 true 时执行代码，当条件为 false 时执行其他代码

* _if...else if....else 语句_

使用该语句来选择多个代码块之一来执行

* _switch 语句_

使用该语句来选择多个代码块之一来执行

* ## for

```js
for (var i=0;i<cars.length;i++)
{
document.write(cars[i] + "<br>");
}

var person={fname:"John",lname:"Doe",age:25};

for (x in person)
  {
  txt=txt + person[x];
  }
```

* ## while

```js
while (i<5)
  {
  x=x + "The number is " + i + "<br>";
  i++;
  }
```

# 2.函数

* ## 闭包：

有权访问另一个函数作用域内变量的函数都是闭包。这里 inc 函数访问了构造函数 a 里面的变量 n，所以形成了一个闭包。

```js
function a(){
  var n = 0;
  function inc() {
    n++;
    console.log(n);
  }
  inc(); 
  inc(); 
}
a(); //控制台输出1，再输出2

function a(){
  var n = 0;
  this.inc = function () {
    n++; 
    console.log(n);
  };
}
var c = new a();
c.inc();  //控制台输出1
c.inc();  //控制台输出2
```

* ## 错误：

当 JavaScript 引擎执行 JavaScript 代码时，会发生各种错误：

* 可能是语法错误，通常是程序员造成的编码错误或错别字。
* 可能是拼写错误或语言中缺少的功能（可能由于浏览器差异）。
* 可能是由于来自服务器或用户的错误输出而导致的错误。

```js
try
  {
  //在这里运行代码
  }
catch(err)
  {
  //在这里处理错误
  }
```



