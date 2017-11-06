# css3过渡——\(transition\)

要实现这一点，必须规定两项内容：

* 规定您希望把效果添加到哪个 CSS 属性上

* 规定效果的时长

```css
div
{
transition: width 2s;
-moz-transition: width 2s;    /* Firefox 4 */
-webkit-transition: width 2s;    /* Safari 和 Chrome */
-o-transition: width 2s;    /* Opera */
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

|  |  |  |  | 属性 | 描述 |
| :--- | :--- | :--- | :--- | :--- | :--- |
|  |  |  |  | transition | 简写属性，用于在一个属性中设置四个过渡属性。 |
|  |  |  |  | transition-property | 规定应用过渡的 CSS 属性的名称。 |
|  |  |  |  | transition-duration | 定义过渡效果花费的时间。默认是 0。 |
| transition-timing-function | 规定过渡效果的时间曲线。默认是 "ease"。         linear ease ease-in ease-out ease-in-out           cubic-bezier\(n,n,n,n\) |  |  |  |  |
|  |  |  |  | transition-delay | 规定过渡效果何时开始。默认是 0。 |

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

# css3动画——（animation）

##### @keyframes

```css
@keyframes myfirst
{
from {background: red;}
to {background: yellow;}
}

@-moz-keyframes myfirst /* Firefox */
{
from {background: red;}
to {background: yellow;}
}

@-webkit-keyframes myfirst /* Safari 和 Chrome */
{
from {background: red;}
to {background: yellow;}
}

@-o-keyframes myfirst /* Opera */
{
from {background: red;}
to {background: yellow;}
}
```

通过规定至少以下两项 CSS3 动画属性，即可将动画绑定到选择器：

* 规定动画的名称
* 规定动画的时长

```css
div
{
animation: myfirst 5s;
-moz-animation: myfirst 5s;    /* Firefox */
-webkit-animation: myfirst 5s;    /* Safari 和 Chrome */
-o-animation: myfirst 5s;    /* Opera */
}
```

```css
@keyframes myfirst
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

@-moz-keyframes myfirst /* Firefox */
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

@-webkit-keyframes myfirst /* Safari 和 Chrome */
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

@-o-keyframes myfirst /* Opera */
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}
```

| 属性 | 描述 |
| :--- | :--- |
| [@keyframes](http://www.w3school.com.cn/cssref/pr_keyframes.asp) | 规定动画。 |
| [animation](http://www.w3school.com.cn/cssref/pr_animation.asp) | 所有动画属性的简写属性，除了 animation-play-state 属性。 |
| [animation-name](http://www.w3school.com.cn/cssref/pr_animation-name.asp) | 规定 @keyframes 动画的名称。 |
| [animation-duration](http://www.w3school.com.cn/cssref/pr_animation-duration.asp) | 规定动画完成一个周期所花费的秒或毫秒。默认是 0。 |
| [animation-timing-function](http://www.w3school.com.cn/cssref/pr_animation-timing-function.asp) | 规定动画的速度曲线。默认是 "ease"。 |
| [animation-delay](http://www.w3school.com.cn/cssref/pr_animation-delay.asp) | 规定动画何时开始。默认是 0。 |
| [animation-iteration-count](http://www.w3school.com.cn/cssref/pr_animation-iteration-count.asp) | 规定动画被播放的次数。默认是 1。 |
| [animation-direction](http://www.w3school.com.cn/cssref/pr_animation-direction.asp) | 规定动画是否在下一周期逆向地播放。默认是 "normal"。 |
| [animation-play-state](http://www.w3school.com.cn/cssref/pr_animation-play-state.asp) | 规定动画是否正在运行或暂停。默认是 "running"。 |
| [animation-fill-mode](http://www.w3school.com.cn/cssref/pr_animation-fill-mode.asp) | 规定对象动画时间之外的状态。 |



