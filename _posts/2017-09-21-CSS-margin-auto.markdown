---
layout: post
title: CSS  margin:0 auto;
date: 2017-09-21 13:40:00.000000000 +09:00
tags: css ,layout
---

***
+  想要居中 div 没那么简单
  +  div 是块元素,默认占满整个父元素的宽度
    +  `margin:  0 auto;` 自然就无效
  +  照理说将 div 设置为 float,包裹后就能设置 margin,但是 auto 无效为什么?
    +  auto 是相对于父元素而言的, 而父元素的 width 是由margin, border, padding 和 content 等因素决定的,如果说没有设置 div 的width,又要 margin:0 auto, 简直是又想马儿跑,又想马儿不吃草!
  +  增加 float 更糟糕,元素具有了包裹性,脱离标准流,没有了可供参考的父元素宽度
  + 以及 `text-align: center`的居中方式不是说使得 div 居中,而是 div 的内容居中
