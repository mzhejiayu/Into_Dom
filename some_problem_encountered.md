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

## 8月6日
1. 对于css文件的部署，有一个问题就是多余css的问题，有一些css中的一些类对于某些页面无用，如果都放在里面，会导致大量的冗余的情况，增大不必要流量。对于像导航栏或者footer这些元素的话，可以有一个统一的文件。而其他特殊功能性的东西，应该放在其他单独的文件中
2. 有一个神奇的选择器，可以修改input中placeholder中文字的
`::-moz-placeholder,::-webkit-input-placeholder, :-ms-input-placeholder`

## 8月10日
1. 在开发网站之前，可以定义的一些基本的元素需要提前规定`颜色` `边距` `字号` `边框半径`，这样子看来，如果使用sass＋oocss的话，会非常方便维护，因为sass中一个类可以去继承其他的类，这样css和html都有很高的可维护性！
