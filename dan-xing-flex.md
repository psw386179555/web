# Flex 是 Flexible Box 的缩写，意为"弹性布局"

## 1.了解flex

```css
.box{
  display: flex;
}
.box{
  display: inline-flex;
}
.box{
  display: -webkit-flex; /* Safari */
  display: flex;
}
```

* 任何一个容器都可以指定为 Flex 布局。
* 行内元素也可以使用 Flex 布局。
* Webkit 内核的浏览器，必须加上`-webkit`前缀。
* 设为 Flex 布局以后，子元素的`float`、`clear`和`vertical-align`属性将失效。

## 2.基本概念

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071004.png)

* 容器默认存在两根轴：水平的主轴（main axis）和垂直的交叉轴（cross axis）。主轴的开始位置（与边框的交叉点）叫做`main start`，结束位置叫做`main end`；交叉轴的开始位置叫做`cross start`，结束位置叫做`cross end`。
* 项目默认沿主轴排列。单个项目占据的主轴空间叫做`main size`，占据的交叉轴空间叫做`cross size`。

## 3.容器的属性

* flex-direction
  （主轴的方向（即项目的排列方向）。）

```css
.box {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071005.png)

* flex-wrap

```
.box{
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071006.png)

* flex-flow

```
.box {
  flex-flow: <flex-direction> || <flex-wrap>;
}
```

* justify-content

```
.box {
  justify-content: flex-start | flex-end | center | space-between | space-around;
}
```

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071010.png)

* align-items

```
.box {
  align-items: flex-start | flex-end | center | baseline | stretch;
}
```

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071011.png)

* align-content

```
.box {
  align-content: flex-start | flex-end | center | space-between | space-around | stretch;
}
```

![](http://www.ruanyifeng.com/blogimg/asset/2015/bg2015071012.png)

