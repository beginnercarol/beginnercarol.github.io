---
layout: post
title: CSS  圣杯布局
date: 2017-09-19 16:46:00.000000000 +09:00
tags: css ,layout
---
***
[参考资料 holygrail](https://alistapart.com/article/holygrail)

***

+ 中间列应该优先出现在布局中.
+ **`position:relative;float:left;`**
事实上顺序是先 float.再 relative.
`float + margin-left:-100%` 让 left 元素来到 main-container 的 left-padding, 因为 float 是抵住 padding 的,接下来要让 left 进入到 padding 内部,就需要`position:relative + left:-left 的宽度`

```html
<div class="main-container">
  <div class="main column">main</div>
  <div class="left column">left</div>
  <div class="right column">right</div>
</div>
<div class="footer">footer</div>
```

```css
body{
  margin:0;
  padding:0;
  min-width:550px;
}
.main-container{
  padding-left:200px;
  padding-right:150px;
}
.column{
  position:relative;
  float:left;
}
.main{
  width:100%;
  background-color:aqua;
}
.left{
  width:200px;
  right:200px;
  margin-left:-100%;
  background-color:yellow;
}
.right{
  width:150px;
  background-color:pink;
  margin-right:-150px;
}
.footer{
  clear:both;
}
```

+ 为了响应式布局,body 需要增加`min-width`以避免页面崩坏.
`min-width`设置为多少比较合适?
在上面的情况下,`.right`其实是在 center 内部的,所以`min-width`设为200px+200px+150px 即可
但是在这种情况下:
`right`其实是在 `container`的右 padding 中,故 body 的`min-width`应该为 200px+200px+150px+150px

```css
  .right{
    width:150px;
    margin-left: -150px;
    background-color:pink;
    position:relative;
    right:-150px;
  }
```

