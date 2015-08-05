#Position and Sizing
>作者： 马哲家昱
>时间： 2015.7.24

##元素的位置
* 距离父元素的位置
* 距离文档边缘的位置
* 距离视口的位置

##元素的尺寸
* 元素内容尺寸
* 元素外尺寸
* 文档尺寸
    * `document.body.scrollWidth * document.body.scrollHeight`
    * `document.documentElement.scrollWidth * document.documentElement.scrollHeight`

设置body的width:100%其实只是让body.style.width = body.clientWidth，这个时候的如果body子元素中设置width:100%的元素就没有充满整个文档的效果。尤其是对于导航条，这是非常讨厌的。
使用下面的代码，让你的网页摆脱这种问题吧。
```javascript
    document.onresize=function(){
        document.body.style.width = (document.documentElement.scrollWidth || document.body.scrollWidth) + "px";
    }
```
