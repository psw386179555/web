# html5的视频

```
<video src="movie.ogg" controls="controls">
</video>


<video src="movie.ogg" width="320" height="240" controls="controls">
Your browser does not support the video tag.
</video>
```

##### &lt;video&gt; 标签的属性

| 属性 | 值 | 描述 |
| :--- | :--- | :--- |
| autoplay | autoplay | 如果出现该属性，则视频在就绪后马上播放。 |
| ~~controls~~ | controls | 如果出现该属性，则向用户显示控件，比如播放按钮。 |
| height | pixels | 设置视频播放器的高度。 |
| loop | loop | 如果出现该属性，则当媒介文件完成播放后再次开始播放。 |
| preload | preload | 如果出现该属性，则视频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。 |
| src | url | 要播放的视频的 URL。 |
| width | pixels | 设置视频播放器的宽度。 |

```
<!DOCTYPE html> 
<html> 
<body> 

<div style="text-align:center;">
  <button onclick="playPause()">播放/暂停</button> 
  <button onclick="makeBig()">大</button>
  <button onclick="makeNormal()">中</button>
  <button onclick="makeSmall()">小</button>
  <br /> 
  <video id="video1" width="420" style="margin-top:15px;">
    <source src="/example/html5/mov_bbb.mp4" type="video/mp4" />
    <source src="/example/html5/mov_bbb.ogg" type="video/ogg" />
    Your browser does not support HTML5 video.
  </video>
</div> 

<script type="text/javascript">
var myVideo=document.getElementById("video1");

function playPause()
{ 
if (myVideo.paused) 
  myVideo.play(); 
else 
  myVideo.pause(); 
} 

function makeBig()
{ 
myVideo.width=560; 
} 

function makeSmall()
{ 
myVideo.width=320; 
} 

function makeNormal()
{ 
myVideo.width=420; 
} 
</script> 

</body> 
</html>
```

# html5的音频

```
<audio src="song.ogg" controls="controls">
</audio>
```

#### &lt;audio&gt; 标签的属性

| 属性 | 值 | 描述 |
| :--- | :--- | :--- |
| autoplay | autoplay | 如果出现该属性，则音频在就绪后马上播放。 |
| controls | controls | 如果出现该属性，则向用户显示控件，比如播放按钮。 |
| loop | loop | 如果出现该属性，则每当音频结束时重新开始播放。 |
| preload | preload | 如果出现该属性，则音频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。 |
| src | url | 要播放的音频的 URL。 |



# html5的拖放

```
<!DOCTYPE HTML>
<html>
<head>
<style type="text/css">
#div1 {width:198px; height:66px;padding:10px;border:1px solid #aaaaaa;}
</style>
<script type="text/javascript">
function allowDrop(ev)
{
ev.preventDefault();
}

function drag(ev)
{
ev.dataTransfer.setData("Text",ev.target.id);
}

function drop(ev)
{
ev.preventDefault();
var data=ev.dataTransfer.getData("Text");
ev.target.appendChild(document.getElementById(data));
}
</script>
</head>
<body>

<p>请把 W3School 的图片拖放到矩形中：</p>

<div id="div1" ondrop="drop(event)" ondragover="allowDrop(event)"></div>
<br />
<img id="drag1" src="/i/eg_dragdrop_w3school.gif" draggable="true" ondragstart="drag(event)" />

</body>
</html>

```

## 设置元素为可拖放

首先，为了使元素可拖动，把 draggable 属性设置为 true ：

```
<img draggable="true" />
```

## 拖动什么 - ondragstart 和 setData\(\)

然后，规定当元素被拖动时，会发生什么。

在上面的例子中，ondragstart 属性调用了一个函数，drag\(event\)，它规定了被拖动的数据。

dataTransfer.setData\(\) 方法设置被拖数据的数据类型和值：

```
function drag(ev)
{
ev.dataTransfer.setData("Text",ev.target.id);
}
```

在这个例子中，数据类型是 "Text"，值是可拖动元素的 id \("drag1"\)。

## 放到何处 - ondragover

ondragover 事件规定在何处放置被拖动的数据。

默认地，无法将数据/元素放置到其他元素中。如果需要设置允许放置，我们必须阻止对元素的默认处理方式。

这要通过调用 ondragover 事件的event.preventDefault\(\) 方法：

```
event.preventDefault()
```

## 进行放置 - ondrop

当放置被拖数据时，会发生 drop 事件。

在上面的例子中，ondrop 属性调用了一个函数，drop\(event\)：

```
function drop(ev)
{
ev.preventDefault();
var data=ev.dataTransfer.getData("Text");
ev.target.appendChild(document.getElementById(data));
}
```

### 代码解释：

* 调用 preventDefault\(\) 来避免浏览器对数据的默认处理（drop 事件的默认行为是以链接形式打开）
* 通过 dataTransfer.getData\("Text"\) 方法获得被拖的数据。该方法将返回在 setData\(\) 方法中设置为相同类型的任何数据。
* 被拖数据是被拖元素的 id \("drag1"\)
* 把被拖元素追加到放置元素（目标元素）中



