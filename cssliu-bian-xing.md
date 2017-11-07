六边形

```css
.boxF, .boxS, .boxT, .overlay
{
    width: 200px;
    height: 250px;
    overflow: hidden;
}
.boxF, .boxS
{
    visibility: hidden;
}
.boxF
{
    transform: rotate(120deg);
    float: left;
    margin-left: 10px;
    -ms-transform: rotate(120deg);
    -moz-transform: rotate(120deg);
    -webkit-transform: rotate(120deg);
}
.boxS
{
    transform: rotate(-60deg);
    -ms-transform: rotate(-60deg);
    -moz-transform: rotate(-60deg);
    -webkit-transform: rotate(-60deg);
}
.boxT
{
    transform: rotate(-60deg);
    background: no-repeat 50% center;
    background-size: 125% auto;
    -ms-transform: rotate(-60deg);
    -moz-transform: rotate(-60deg);
    -webkit-transform: rotate(-60deg);
    visibility: visible;
}
```

html部分

```css
<div class="boxF">
<div class="boxS">
<div class="boxT" style="background-image: url();"></div>
</div>
</div>
```



