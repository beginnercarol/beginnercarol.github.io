---
layout: post
title: CSS flaot+absolute
date: 2017-09-23 11:42:00.000000000 +09:00
tags: css
---
***


```
sidebar{
	float:right;/* 两行无所谓先后 */
	position: absolute;
}
```


设置为 right 更为直观, 可以看到 float "失效了"


```
sidebar{
	float:right;/* 两行无所谓先后 */
	position:  relative;
}
```

修改为relative 之后,float 并不失效,而是根据浮动后的位置再进行 relative 定位.
一般用于把 在下一行的元素提到上一行来

***
之前提到[float 元素,百分值不适用](https://www.evernote.com/shard/s245/nl/50832658/1ea54eee-d03a-495c-8b80-66d929621789/)
因此但凡这个元素是 float,就不能用百分值设置长和宽
***">

