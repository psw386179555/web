# css3过渡——\(transition\)

要实现这一点，必须规定两项内容：

* 规定您希望把效果添加到哪个 CSS 属性上

* 规定效果的时长

```css
div
{
transition: width 2s;
-moz-transition: width 2s;	/* Firefox 4 */
-webkit-transition: width 2s;	/* Safari 和 Chrome */
-o-transition: width 2s;	/* Opera */
}
```

如需向多个样式添加过渡效果，请添加多个属性，由逗号隔开：

```css
div
{
transition: width 2s, height 2s, transform 2s;
-moz-transition: width 2s, height 2s, -moz-transform 2s;
-webkit-transition: width 2s, height 2s, -webkit-transform 2s;
-o-transition: width 2s, height 2s,-o-transform 2s;
}
```

| 属性 | 描述 |
| :--- | :--- |
| transition | 简写属性，用于在一个属性中设置四个过渡属性。 |
| transition-property | 规定应用过渡的 CSS 属性的名称。 |
| transition-duration | 定义过渡效果花费的时间。默认是 0。 |
| transition-timing-function | 规定过渡效果的时间曲线。默认是 "ease"。         linear ease ease-in ease-out ease-in-out           cubic-bezier\(n,n,n,n\) |   |   |   |   |
| transition-delay | 规定过渡效果何时开始。默认是 0。 |

简写：

```css
div
{
transition: width 1s linear 2s;
/* Firefox 4 */
-moz-transition:width 1s linear 2s;
/* Safari and Chrome */
-webkit-transition:width 1s linear 2s;
/* Opera */
-o-transition:width 1s linear 2s;
}
```



