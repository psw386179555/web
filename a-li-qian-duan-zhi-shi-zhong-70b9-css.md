# 1.position

| absolute | 生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 |
| :--- | :--- |
| fixed | 生成绝对定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 |
| relative | 生成相对定位的元素，相对于其正常位置进行定位。因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。 |
| static | 默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。 |
| inherit | 规定应该从父元素继承 position 属性的值。 |

# 2.display

| none | 此元素不会被显示。 |
| :--- | :--- |
| block | 此元素将显示为块级元素，此元素前后会带有换行符。 |
| inline | 默认。此元素会被显示为内联元素，元素前后没有换行符。 |
| inline-block | 行内块元素。（CSS2.1 新增的值） |
| list-item | 此元素会作为列表显示。 |
| run-in | 此元素会根据上下文作为块级元素或内联元素显示。 |
| compact | CSS 中有值 compact，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| marker | CSS 中有值 marker，不过由于缺乏广泛支持，已经从 CSS2.1 中删除。 |
| table | 此元素会作为块级表格来显示（类似 &lt;table&gt;），表格前后带有换行符。 |
| inline-table | 此元素会作为内联表格来显示（类似 &lt;table&gt;），表格前后没有换行符。 |
| table-row-group | 此元素会作为一个或多个行的分组来显示（类似 &lt;tbody&gt;）。 |
| table-header-group | 此元素会作为一个或多个行的分组来显示（类似 &lt;thead&gt;）。 |
| table-footer-group | 此元素会作为一个或多个行的分组来显示（类似 &lt;tfoot&gt;）。 |
| table-row | 此元素会作为一个表格行显示（类似 &lt;tr&gt;）。 |
| table-column-group | 此元素会作为一个或多个列的分组来显示（类似 &lt;colgroup&gt;）。 |
| table-column | 此元素会作为一个单元格列显示（类似 &lt;col&gt;） |
| table-cell | 此元素会作为一个表格单元格显示（类似 &lt;td&gt; 和 &lt;th&gt;） |
| table-caption | 此元素会作为一个表格标题显示（类似 &lt;caption&gt;） |
| inherit | 规定应该从父元素继承 display 属性的值。 |

# 3.float

| left | 元素向左浮动。 |
| :--- | :--- |
| right | 元素向右浮动。 |
| none | 默认值。元素不浮动，并会显示在其在文本中出现的位置。 |
| inherit | 规定应该从父元素继承 float 属性的值。 |

# 4.clear

| left | 在左侧不允许浮动元素。 |
| :--- | :--- |
| right | 在右侧不允许浮动元素。 |
| both | 在左右两侧均不允许浮动元素。 |
| none | 默认值。允许浮动元素出现在两侧。 |
| inherit | 规定应该从父元素继承 clear 属性的值。 |

# 5.盒子模型

![](http://www.w3school.com.cn/i/ct_boxmodel.gif)

在 CSS 中，width 和 height 指的是内容区域的宽度和高度。增加内边距、边框和外边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸。

# 6.line-height

| normal | 默认。设置合理的行间距。 |
| :--- | :--- |
| number | 设置数字，此数字会与当前的字体尺寸相乘来设置行间距。 |
| length | 设置固定的行间距。 |
| % | 基于当前字体尺寸的百分比行间距。 |
| inherit | 规定应该从父元素继承 line-height 属性的值。 |

# 7.vertical-align

| baseline | 默认。元素放置在父元素的基线上。 |
| :--- | :--- |
| sub | 垂直对齐文本的下标。 |
| super | 垂直对齐文本的上标 |
| top | 把元素的顶端与行中最高元素的顶端对齐 |
| text-top | 把元素的顶端与父元素字体的顶端对齐 |
| middle | 把此元素放置在父元素的中部。 |
| bottom | 把元素的顶端与行中最低的元素的顶端对齐。 |
| text-bottom | 把元素的底端与父元素字体的底端对齐。 |
| length |  |
| % | 使用 "line-height" 属性的百分比值来排列此元素。允许使用负值。 |
| inherit | 规定应该从父元素继承 vertical-align 属性的值。 |

# 8.white-space

| normal | 默认。空白会被浏览器忽略。 |
| :--- | :--- |
| pre | 空白会被浏览器保留。其行为方式类似 HTML 中的 &lt;pre&gt; 标签。 |
| nowrap | 文本不会换行，文本会在在同一行上继续，直到遇到 &lt;br&gt; 标签为止。 |
| pre-wrap | 保留空白符序列，但是正常地进行换行。 |
| pre-line | 合并空白符序列，但是保留换行符。 |
| inherit | 规定应该从父元素继承 white-space 属性的值。 |

# 9.word-break

| normal | 使用浏览器默认的换行规则。 |
| :--- | :--- |
| break-all | 允许在单词内换行。 |
| keep-all | 只能在半角空格或连字符处换行。 |

---

# 10.background

* background-color 规定要使用的背景颜色。
* background-position  规定背景图像的位置

| top lefttop centertop rightcenter leftcenter centercenter rightbottom leftbottom centerbottom right | 如果您仅规定了一个关键词，那么第二个值将是"center"。默认值：0% 0%。 |
| :--- | :--- |
| x% y% | 第一个值是水平位置，第二个值是垂直位置。左上角是 0% 0%。右下角是 100% 100%。如果您仅规定了一个值，另一个值将是 50%。 |
| xpos ypos | 第一个值是水平位置，第二个值是垂直位置。左上角是 0 0。单位是像素 \(0px 0px\) 或任何其他的 CSS 单位。如果您仅规定了一个值，另一个值将是50%。您可以混合使用 % 和 position 值。 |

* background-size  规定背景图片的尺寸。

| 设置背景图像的高度和宽度。第一个值设置宽度，第二个值设置高度。如果只设置一个值，则第二个值会被设置为 "auto"。 | length |
| :--- | :--- |


| percentage | 以父元素的百分比来设置背景图像的宽度和高度。第一个值设置宽度，第二个值设置高度。如果只设置一个值，则第二个值会被设置为 "auto"。 |
| :--- | :--- |


| cover | 把背景图像扩展至足够大，以使背景图像完全覆盖背景区域。背景图像的某些部分也许无法显示在背景定位区域中。 |
| :--- | :--- |


| contain | 把图像图像扩展至最大尺寸，以使其宽度和高度完全适应内容区域。 |
| :--- | :--- |


* background-repeat  规定如何重复背景图像。
* background-origin  规定背景图片的定位区域。
* background-clip  规定背景的绘制区域。
* background-attachment   规定背景图像是否固定或者随着页面的其余部分滚动。
* background-image    规定要使用的背景图像。
  





