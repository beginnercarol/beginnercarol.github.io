---
layout: post
title: JS hasChildNodes
date: 2017-10-10 12:37:00.000000000 +09:00
tags: js 
---

***

# JS hasChildNodes

空格也会被解释为一个文本节点
当没有子节点时,返回一个空数组
当有空格的时候(即有子节点),返回`true`

[示例](https://codepen.io/CarolBeginner/pen/GMdrby?editors=1111 )

***
有几种判断元素是否包含子元素的方法:
1. node.hasChildNodes()
2. node.firstChild != null (or just node.firstChild)
3. node.childNodes && node.childNodes.length (or node.childNodes.length > 0)

此外还有一个 HTML5 拓展的方法:
#### children
+ 只包含元素中同样还是元素的子节点(没有包含在标签内的文本,空格都不包含在内!)