```js
function PPTBox() {
    this.uid = PPTBoxHelper.getId();
    PPTBoxHelper.instance[this.uid] = this;
    this._$ = function (id) {
        return document.getElementById(id)
    };
    this.width = 378;
    this.height = 246;
    this.picWidth = 15;
    this.picHeight = 12;
    this.autoplayer = 4;
    this.target = "_blank";
    this._box = [];
    this._curIndex = 0;
}

PPTBox.prototype = {
    _createMainBox:function () {
        let flashBoxWidth = this.width * this._box.length + 5;
        let html = "<div id='"+this.uid+"_mainbox' class='mainbox' style='width: "+(this.width)+"px;height="+(this.height+2)+"px'>";
        html += "<div id='"+(this.uid)+"_flashbox' class='flashbox' style='width:"+flashBoxWidth+"px;height: "+(this.height+2)+"px'></div>";
        html += "<div id='"+(this.uid)+"_imagebox' class='imagebox' style='"+this.width+"px;height: "+(this.picHeight+2)+"px;top:-"+(this.picHeight+20)+"px;'></div>";
        html += "</div>";
        document.write(html);
    },

    _init:function () {
        let picStyle = "";
        let eventString =  "PPTBoxHelper.instance['"+this.uid+"']";
        let imageHtml = "";
        let flashBox = "";
        for(let i = 0; i<this._box.length;i++){
            let param = this._box[i];
            flashBox +=  this.flashHTML(param.url,this.width,this.height,i);
            imageHtml = "<div class='bitdiv "+((i == 0) ? "curimg":"defimg")+"' title='"+param.title+"' src='bit01.gif' "+picStyle+" onclick=\""+eventString+".clickPic("+i+")\" onmouseover=\""+eventString+".mouseoverPic("+i+")\"></div>"+imageHtml;
        }
        this._$(this.uid+"_flashbox").innerHTML = flashBox;
        this._$(this.uid+"_imagebox").innerHTML = imageHtml;
    },

    _play:function () {
        clearInterval(this._autoplay);
        let idx = this._curIndex+1;
        if(idx>=this._box.length){idx=0;}
        this.changeIndex(idx);
        let eventstr = "PPTBoxHelper.instance['"+this.uid+"']._play()";
        this._autoplay = setInterval(eventstr,this.autoplayer*1000);
    },

    flashHTML : function(url,width,height,idx) {
        let isFlash = url.substring(url.lastIndexOf('.')+1).toLowerCase()=="swf";
        let html = "";
        if(isFlash){
            html = "<object classid='clsid:D27CDB6E-AE6D-11cf-96B8-444553540000' "
                + "codebase='http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=7,0,19,0' width='"+width+"' height='"+height+"'>"
                + "<param name=\"movie\" value=\""+url+"\" />"
                + "<param name='quality' value='high' />"
                + "<param name='wmode' value='transparent'>"
                + "<embed src='"+url+"' quality='high' wmode='opaque' pluginspage='http://www.macromedia.com/go/getflashplayer'"
                +"  type='application/x-shockwave-flash' width="+width+" height='"+height+"'></embed>"
                +"  </object>";
        } else {
            let eventstr = "PPTBoxHelper.instance['"+this.uid+"']";
            let style = "";
            if(this._box[idx].href){
                style = "cursor:pointer"
            }
            html="<img src='"+url+"' style='width:"+width+"px;height:"+height+"px;"+style+"' onclick = \""+eventstr+".clickPic("+idx+")\"/>";
        }
        return html;
    },
    changeIndex:function (idx) {
        moveElement(this.uid+"_flashbox",-(idx*this.width),1);
        let imgs = this._$(this.uid+"_imagebox").getElementsByTagName("div");
        imgs[this._box.length-1-this._curIndex].className = "bitdiv defimg";
        imgs[this._box.length-1-idx].className = "bitdiv curimg";
        this._curIndex = idx;
    },

    mouseoverPic:function (idx) {
        this.changeIndex(idx);
        if (this.autoplayer > 0){
            clearInterval(this._autoplay);
            let eventString = "PPTBoxHelper.instance['"+this.uid+"']._play()";
            this._autoplay = setInterval(eventString,this.autoplayer*1000);
        }
    },

    clickPic:function (idx) {
        let param = this._box[idx];
        if (param.href && param.href != ""){
            window.open(param.href,this.target)
        }
    },
    add:function (item) {
        this._box[this._box.length] = item;
    },
    show:function () {
        this._createMainBox();
        this._init();
        if(this.autoplayer>0){
            let eventString = "PPTBoxHelper.instance['"+this.uid+"']._play()";
            this._autoplay = setInterval(eventString,this.autoplayer*1000);
        }
    }
};


let PPTBoxHelper = {
    count:0,
    instance:{},
    getId: function() { return '_ppt_box-' + (this.count++); }
};

function moveElement(elementID,final_x,interval) {
    if(!document.getElementById) return false;
    if (!document.getElementById(elementID)) return false;
    let ele = document.getElementById(elementID);
    if(ele.movement){
        clearTimeout(ele.movement)
    }
    if(!ele.style.left){
        ele.style.left = "0px";
    }
    let xpos = parseInt(ele.style.left);
    if (xpos == final_x){
        return true;
    }
    if (xpos < final_x) {
        let dist = Math.ceil((final_x - xpos)/5);
        xpos = xpos + dist;
    }
    if (xpos > final_x) {
        let dist = Math.ceil((xpos - final_x)/5);
        xpos = xpos - dist;
    }
    ele.style.left = xpos + "px";
    let repeat = "moveElement('"+elementID+"',"+final_x+","+interval+")";
    ele.movement = setTimeout(repeat,interval);
}
```



