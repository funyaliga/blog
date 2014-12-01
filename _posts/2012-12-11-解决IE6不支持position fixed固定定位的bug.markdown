---
layout: post
title:  "解决IE6不支持position:fixed固定定位的bug"
date:   2012-12-11 11:16:00
category: web
permalink: /12131
uid: 12131
---

### 在IE6中实现 position:fixed; 的办法: ###

**浏览器头部固定**

```css
.fixed_top {
	position: fixed;
	top: 0px;
}
/* IE6 头部固定 */
* html .fixed_top {
	position: absolute;
	bottom: auto;
	top: expression(eval(document.documentElement.scrollTop));
}
```

<!-- read more -->

**浏览器底部固定**

```css
.fixed_bottom{
	position: fixed;
	bottom: 0px;
}
/* IE6 底部固定  */
* html .fixed_bottom{
	position: absolute;
	bottom: auto;
	top: expression(eval(document.documentElement.scrollTop+document.documentElement.clientHeight-this.offsetHeight-(parseInt(this.currentStyle.marginTop,10)||0)-(parseInt(this.currentStyle.marginBottom,10)||0)));
}
```

这两段代码只能实现在最底部或最顶部，再配合margin可控制元素的位置

**另外还有两个，左侧固定和右侧固定**

```css
.fixed_left {position:fixed;right:auto;left:0px;}
/* IE6 左侧固定 */
* html .fixed_left{position:absolute;right:auto;left:expression(eval(document.documentElement.scrollLeft));}
.fixed_right {position:fixed;right:0px;left:auto;}
<br>/* IE6 右侧固定 */ 
* html .fixed_right{position:absolute;right:auto;left:expression(eval(document.documentElement.scrollLeft+document.documentElement.clientWidth-this.offsetWidth)-(parseInt(this.currentStyle.marginLeft,10)||0)-(parseInt(this.currentStyle.marginRight,10)||0));}
```

### IE6抖动问题的解决 ###

在实现页面滚动的时候，被固定定位的元素在IE6会出现闪动现象.

**解决方法：**

```css
* html,* html body {
	background-image:url(about:blank);
	background-attachment:fixed;
}
```

或

```css
* html,* html body { 
	_text-overflow:ellipsis; 
}
```

查看demo：<a href="/demo/ie6_fixed_demo.html" target="_blank">ie6 fixed</a>