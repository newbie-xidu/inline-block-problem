﻿当我们用inline-block代替float的时候，会出现元素之间有空隙的情况，如图


![这里写图片描述](http://img.blog.csdn.net/20170214111958413?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvd2F0ZXJtZWxvbl94aQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

再这里我就列举几种简单的办法：

1、元素之间出现空隙是因为标签段之间的空格，所以只要去掉标签端之间的空格即可。

```
//结构一
<div class="body" >
			<div class="box">	
			</div><div class="box">
			</div><div class="box">
			</div><div class="box">
			</div><div class="box">
			</div>
		</div>
//结构二
<div class="body" >
			<div class="box"></div
			><div class="box"></div
			><div class="box"></div
			><div class="box"></div
			><div class="box"></div>
		</div>
//结构三
<div class="body" >
			<div class="box"></div><!--
			--><div class="box"></div><!--
			--><div class="box"></div><!--
			--><div class="box"></div><!--
			--><div class="box"></div>
		</div>
```

2、子元素设置margin：-4px; 这种解决方法并不完美，如果你的父元素设置的字号不一样，可能你的“-4px”就不能解决问题。况且在Chrome中你需要设置margin:-8px;才能实现同等的效果。

```
.box{
	width: 50px;
	height: 50px;
	display: inline-block;
	background: lightcoral;
	margin: 0 auto;
	margin-right:-8px;
}
```
3、设置父元素字体为 0 。

```
.body{
	width: 300px;
	font-size: 0;
     /*-webkit-text-size-adjust:none;*/
	background: lightblue;
}
```
4、用浮动的方法也可以解决。

暂时就写这些以后遇到再慢慢补充。

