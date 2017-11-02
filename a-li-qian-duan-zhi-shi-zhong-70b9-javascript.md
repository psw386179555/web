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

```js
<script>
function myFunction()
{
try
  {
  var x=document.getElementById("demo").value;
  if(x=="")    throw "empty";
  if(isNaN(x)) throw "not a number";
  if(x>10)     throw "too high";
  if(x<5)      throw "too low";
  }
catch(err)
  {
  var y=document.getElementById("mess");
  y.innerHTML="Error: " + err + ".";
  }
}
</script>
```

* ## with

在严格模式下不能使用with语句。with的作用之一是简化代码，with的缺点：性能问题、语义不明，调试困难

```js
function Lakers() {  
       this.name = "kobe bryant";  
       this.age = "28";  
       this.gender = "boy";  
}  
var people=new Lakers();  
with(people)  
{  
       var str = "姓名: " + name + "<br>";  
       str += "年龄：" + age + "<br>";  
       str += "性别：" + gender;  
       document.write(str);  
}  
```

* ## eval

```js
<script type="text/javascript">

eval("x=10;y=20;document.write(x*y)")

document.write(eval("2+2"))

var x=10
document.write(eval(x+17))

</script>
```

* ## 查找

**document.getElementById\(\)**接受一个参数：要取得的元素的ID，查找到则返回该元素，反之返回null。

**document.getElementsByTagName\(\)**接受一个参数：要取得的元素标签名。

**document.getElementsByName\(\)**顾名思义返回带有给定name特性的所有元素。



**querySelector\(\)**该方法接受一个css选择符，返回与该模式匹配的第一个元素，没找到则返回null。

```js
//获取body元素
var body=document.querySelector("body");
    
//获取有ID的元素
var myDiv=document.querySelector("#myDiv");
    
//获取有class为choose的第一个元素
var choose=document.querySelector(".choose");
```

**querySelectorAll\(\)**该方法也接受一个css选择符，只不过返回的是NodeList实例，没找到NodeList就是空的。

```js
//获取em元素
var ems=document.querySelectorAll("em");
    
//获取class为choose的所有元素
var choose=document.querySelectorAll(".choose");
```

**classList**也是HTML5新增的操作类的方式，具有length属性，

```js
//删除一个类
div.classList.remove("class");
//新增一个类
div.classList.add("class");
//切换一个类
div.classList.toggle("class");
//确定是否包含某个类
if(div.classList.contains("class")){
}
//迭代类名
for(var i=0,len=div.classList.length; i<len;i++){
}
```

* ## 隐式原型

每个函数function都有一个prototype，即原型。这里再加一句话——每个对象都有一个\_\_proto\_\_，可成为隐式原型。

obj.\_\_proto\_\_和Object.prototype的属性一样！这么巧！答案就是一样。obj这个对象本质上是被Object函数创建的，因此obj.\_\_proto\_\_=== Object.prototype。我们可以用一个图来表示。

![](http://images.cnitblog.com/blog/138012/201409/181509180812624.png)

* ## prototype原型

每个函数都有一个属性叫做prototype。这个prototype的属性值是一个对象（属性的集合，再次强调！），默认的只有一个叫做constructor的属性，指向这个函数本身。![](http://images.cnitblog.com/blog/138012/201409/172130097842386.png)

* ## 内置对象

JS中内置了17个对象，常用的是Array对象、Date对象、正则表达式对象、string对象、Global对象 

**Array对象中常用方法**：   
concat（）：表示把几个数组合并成一个数组。   
Join（）：返回字符串值，其中包含了连接到一起的数组的所有元素，元素由指定的分隔符分隔开来。   
Pop（）：移除数组最后一个元素。   
Shift（）：移除数组中第一个元素。   
Slice（start，end）：返回数组中的一段。   
Push（）：往数组中新添加一个元素，返回最新长度。   
Sort（）：对数组进行排序。   
Reverse（）：反转数组的排序。   
toLocaleString\(\);返回当前系统时间   
Array对象属性常用的只有一个：   
Length：表示取得当前数组长度   
  
**Global对象**  
是一个固有对象，目的是把所有的全局方法集中在一个对象中。   
Global没有语法，直接调用其方法。   
escape（）: 对 String 对象编码以便它们能在所有计算机上可读.   
escape\(charString\)   
必选项 charstring 参数是要编码的任意 String 对象或文字。   
isNaN\(\):判断一个值是否是NaN。   
parseInt（）：返回由字符串得到的整数   
  
**正则表达式对象**  
本对象包含正则表达式模式以及表明如何应用模式的标志。   
语法 1   
re = /pattern/\[flags\]   
  
语法 2   
re = new RegExp\("pattern",\["flags"\]\)   
re为将要赋值正则表达式模式的变量名   
pattern为正则表达式   
flags为标记：有如下3中   
1：g（全文查找）   
2：i（忽略大小写）   
3：m（多行查找）   
当预先知道查找字符串时用语法 1。当查找字符串经常变动或不知道时用语法 2，比如由用户输入得到的字符串。  
  
**String对象**  
charAt\(\):返回指定索引的位置的字符   
concat（）：返回字符串值，表示两个或多个字符串的连接   
match（）：使用正则表达式模式对字符串执行查找，并将包含查找结果最为结果返回   
function MatchDemo\(\){   
   var r, re;         // 声明变量。   
   var s = "The rain in Spain falls mainly in the plain";   
   re = /ain/i;    // 创建正则表达式模式。   
   r = s.match\(re\);   // 尝试匹配搜索字符串。   
   return\(r\);         // 返回第一次出现 "ain" 的地方。   
}   
  
Replace（a，b）：字符b替换a   
Search（stringObject）：指明是否存在相应的匹配。如果找到一个匹配，search 方法将返回一个整数值，指明这个匹配距离字符串开始的偏移位置。如果没有找到匹配，则返回 -1。   
Slice（start，end）：返回字符段片段   
Split（）：字符串拆分   
Substr（start，length）：字符串截取   
Substring（start，end）取得指定长度内的字符串   
toUpperCase（）：返回一个字符串，该字符串中的所有字母都被转化为大写字母。   
toLowerCase（）：返回一个字符串，该字符串中的所有字母都被转化为小写字母。

**Math对象**

ceil\(\)：向上取整。

floor\(\):向下取整。

round\(\):四舍五入。

random\(\):取随机数。



**Date对象**

get/setDate\(\)：返回或设置日期。

get/setFullYear\(\):返回或设置年份，用四位数表示。

get/setYear\(\):返回或设置年份。

get/setMonth\(\):返回或设置月份。0为一月

get/setHours\(\):返回或设置小时，24小时制

get/setMinutes\(\):返回或设置分钟数。

get/setSeconds\(\):返回或设置秒钟数。

get/setTime\(\):返回或设置时间（毫秒为单位）



