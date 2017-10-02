---
layout: post
title: CSS background
date: 2017-10-02 08:50:00.000000000 +09:00
tags: css 
---

***
+ `background-color & background-image` , `color`在最下层

+ `background-clip:content-box/ padding-box/ border-box`
裁剪背景到一个特定的区域, 关键是裁剪,定位还是 `-origin` 和 `-position`共同决定

+ `background-origin: content-box/ padding-box/ border-box`
    + `-origin`决定的是背景块(div)的载入背景的起始位置

+ `background-position: 
    + 设置背景**图像的起始位置**~~(即设置图像上的位置对应于背景区域的起点).~~
如果设置了 repeat, 就从这个位置开始重复
    + 理解错误,是指以`background-orign`指定的为原点, 像`position left right top bottom`一样指定背景图片出现的位置.
    + 可能的值有:![Alt text](./1506905046084.png)
    + `-position`决定的是图片的起始位置

***
#### Outline
Outline 不是盒模型的组成部分, 是画在 盒子上面(指的是 z-index )boder 外面,~~margin 里面的~~.可以超出 margin 范围

***
#### Background-image 详解

>The background images are drawn on stacking context layers on top of each other. The first layer specified is drawn as if it is closest to the user.

设定多个 url , 第一个 url `z-index`最大,离 user 更近.
注意是同时设定,使用`,`分隔!

+ borders 画在`background-image`上面,而`background-color`在`background-image`下面