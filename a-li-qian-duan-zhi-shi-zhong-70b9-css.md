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

