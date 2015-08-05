# window
*作者:    Mazhejiayu
日期: 2015-7-22*

## 属性
--- 
>***pageYOffset(scrollY) | pageXOffset(scrollX)*** 
这个就是滚轮滑动的距离，当前视口顶部与文档顶部的距离(pageYOffset)
查看[与元素位置、大小有关的属性][size]

---
>***screenLeft | screenRight (firefox 使用 screenX | screenY)***
浏览器在系统屏幕的位置，使用的时候判断一下
查看[与元素位置、大小有关的属性][size]

--- 
>***innerWidth | innerHeight***
文档在可见窗口内的宽度和高度
查看[与元素位置、大小有关的属性][size]
>***opener***
使用window.open()创建的窗口使用window.opener可以获取打开它的那个窗口，window.opener.close()就能将原窗口关闭

---
>***closed***
返回window是否已关闭

 
## 方法


[1]: demo/pageYOffset.html "查看例子"
[2]: demo/screenLeft.html "查看例子"
[3]: demo/opener.html "查看例子"
[size]: position_and_size.md "查看与位置与大小有关的属性"