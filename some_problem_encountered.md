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

## 8月7日
1. 对于css文件的部署，有一个问题就是多余css的问题，有一些css中的一些类对于某些页面无用，如果都放在里面，会导致大量的冗余的情况，增大不必要流量。对于像导航栏或者footer这些元素的话，可以有一个统一的文件。而其他特殊功能性的东西，应该放在其他单独的文件中
2. 有一个神奇的选择器，可以修改input中placeholder中文字的
`::-moz-placeholder,::-webkit-input-placeholder, :-ms-input-placeholder`

## 8月10日
1. 在开发网站之前，可以定义的一些基本的元素需要提前规定`颜色` `边距` `字号` `边框半径`，这样子看来，如果使用sass＋oocss的话，会非常方便维护，因为sass中一个类可以去继承其他的类，这样css和html都有很高的可维护性！

## 8月11日
1. 今天在修改所有的html的导航条的时候，思考到了可维护性的问题，如何将前端开发进行模块化，让整个架构有更高的可维护性，有更好的开发效率，这个是我们需要考虑的问题。如今有sass + compass提供了非常方便的功能`@import` `@mixin`。 使用这个就可将不同功能的css 进行划分在不同的文件当中，然后统一导入到main.scss中进行编译压缩。

## 8月12日

> 相关内容：
[css selector intent](http://csswizardry.com/2012/07/shoot-to-kill-css-selector-intent/)

1. 一个极端的css例子 `html > body > .nav > .header` 可以用简单的 `nav__header` 来代替。与其想方设法去定位一个元素，不如直击目标，为它加上一个语意化的类。这儿有一种非常有用的命命方式叫做BEM(Block Element Modifier)，降低对html标签结构的依赖性

		.header{
			.header__title{
				.header__title__left{
					//scss code
				}
				.header__title__right{
					//scss code
				}
			}
		}

2. css 代码的编写的时候，如果有父子关系的代码，可以使用恰当的缩进为编码人员提供额外的信息，另外，利用注释可以让维护变的方便

		/* 
		 * ^footer(在修改的时候搜索^content)作为一种标签来使用
		 */
		.footer{
		
		}
			.footer-left{
			
			}
			.footer-right{
			
			}
		.header{
		
		}
			.header-left{
			
			}
			.header-right{
			
			}
			
#8月13日
1. 今天花了整整一天的时间解决表单的问题，这个问题非常地恼人。开始validVal来写的验证已经非常好了，不过今天在加入ajax的时候发现了严重的问题，validVal的验证是单次即时的验证，不存在验证栈。因而将验证的插件切换为jquery.validate插件，这个插件对于我来说相对比较新，花了很长时间来适应，但是又回出现很多始料不及的问题，一些小的细节是jquery自作聪明地为用户考虑了，看似方便，但是扩展性比较差。我觉得一个真正有用的验证插件要解决的问题无非如下：
	> 1. 验证事件的触发（用户可以具体设置何时触发），可以使用函数来返回true|false
	> 2. 验证函数栈（一些基础的，用户可以为他们加新的）
	> 3. 下一层过滤出验证成功和失败的事件可以为他们添加处理函数栈
	> 4. 提供验证状态接口（查看表单状态，以及修改的方法），方便用户监控整个表单的状态
	> 5. 提交表单的不同方式（普通，ajax）