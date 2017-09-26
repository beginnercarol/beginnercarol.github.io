---
layout: post
title: CSS margin+percentage
date: 2017-09-24 09:21:00.000000000 +09:00
tags: css , margin
---

***

    <div class="container">
		<main></main>
		<sidebar class="left"></sidebar>
		<sidebar class="right"></sidebar>
	</div>


```
*{
	padding:0;
	margin:0;
}

.container{
	width:100%;
	height:800px;
	padding-left:200px;
	padding-right:150px;
}

main{
	width:100%;
	height:800px;
	background-color:#ddd;
}
```

***
main 继承 container 的 **width**
+ 当 container 不设置`width:100%`时 :
main 的 `width:100%`是 container 继承 html 的100%width 再减去 padding-left 和 padding-right 之后的宽度
+ 当 container 设置为`width:100%`:
那么 padding-left 和 padding-right 是额外增加的宽度(由于没有设置为`box-sizing:border-box`)因此,main 的`width:100%` 就是 container width 的100%(直观来讲就是更宽了)
+ 增加一项`*{
	padding:0;
	margin:0;
	box-sizing:border-box;
}`之后就不会有区别了.因为 width 变成了
 `border+padding+content`
 
***