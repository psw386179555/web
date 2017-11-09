canvas 元素使用 JavaScript 在网页上绘制图像。

画布是一个矩形区域，您可以控制其每一像素。

canvas 拥有多种绘制路径、矩形、圆形、字符以及添加图像的方法。

## 创建 Canvas 元素

向 HTML5 页面添加 canvas 元素。

规定元素的 id、宽度和高度：

```
<canvas id="myCanvas" width="200" height="100"></canvas>
```

## 通过 JavaScript 来绘制

canvas 元素本身是没有绘图能力的。所有的绘制工作必须在 JavaScript 内部完成：

```
<script type="text/javascript">
var c=document.getElementById("myCanvas");
//JavaScript 使用 id 来寻找 canvas 元素：
var cxt=c.getContext("2d");
//然后，创建 context 对象：
//getContext("2d") 对象是内建的 HTML5 对象，拥有多种绘制路径、矩形、圆形、字符以及添加图像的方法。
//下面的两行代码绘制一个红色的矩形：
cxt.fillStyle="#FF0000";
cxt.fillRect(0,0,150,75);
</script>
```

html5 Carvas 的接口文档[http://www.w3school.com.cn/tags/html\_ref\_canvas.asp](http://www.w3school.com.cn/tags/html_ref_canvas.asp "http://www.w3school.com.cn/tags/html\_ref\_canvas.asp")

