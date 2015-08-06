文字，图片垂直，水平居中

body宽度不等于文档宽度造成的混蛋
可以使用hr作为一个中间间隔符，用它的border来制作扯开布局的作用
## 8月6日
1. 制作加载动画框的效果:目前可以使用100vh 和 100vw 来做一个屏幕中的垂直居中，不过目前很多的浏览器还不支持vh 和vw属性，可以使用`display:absolute`，让它针对浏览器的窗口进行定位，当然它的父元素中间不能有任何一个不为`display:static`。
2. 利用现在的技术来做block垂直居中的垂直居中最简单的方法就是
	
		father:{
			position:relative;
		}
		child:{
			position:absolute;
			top:50%;
			transform:translateY(-50%);
		}


	将来还能使用flex布局让块状元素居中
