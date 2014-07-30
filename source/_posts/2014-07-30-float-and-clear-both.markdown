---
layout: post
title: "CSS浮动与清除浮动"
date: 2014-07-30 22:34:27 +0800
comments: true
categories: 
---
**float属性**

在CSS中的相关内容是：float: none | left | right

none：对象不浮动

left：对象浮在左边

right：对象浮在右边

float属性用于设置html标签的浮动样式，它定义元素在哪个方向浮动。在CSS中，任何元素都可以浮动。浮动元素会生成一个块级框（box），而不论它本身是何种元素。<!--more-->（注释：假如在一行之上没有足够空间可供元素浮动，那么该元素会跳至下一行，直到某一行拥有足够的空间为止。）

我们应注意与文字内容靠左（text-align: left）和文字内容靠右（text-align: right）这两个属性的区别，float属性只能针对html标签设置浮动样式。此外，float属性没有居中的浮动样式，需通过设置CSS的margin属性来实现居中。



**清除浮动的几个方法**

在使用float浮动属性进行排版之后，如果没有对子级盒子相应地清除浮动，会造成父级盒子无法被撑开，从而导致父级的背景或边框不能正确显示的问题。

**方法一：首先，介绍最普遍被使用的方法——使用clear: both清除浮动。**

clear属性的语法：

clear: none | both | left | right

none：允许两边都可以有浮动对象

both：不允许有浮动对象

left：不允许左边有浮动对象

right：不允许右边有浮动对象

CSS手册上是这样说明的：该属性的值指出了不允许有浮动对象的边。这个属性是用来控制float属性在文档流的物理位置的。

当元素设置float浮动属性时，其所在的物理位置就已经脱离文档流了，但是大多数时候我们希望文档流能识别float浮动属性，或者是希望后面的元素不被float浮动属性所影响，这时候就需要用clear: both来清除浮动了。

具体方法如下：

首先，为了统一样式，我们新建一个样式选择器命名为“.clear”，并且对应设置选择器样式为“clear: both;”，然后在父级“`</div>`”结束前，添加一行代码`<div class="clear"></div>`，即可实现清除浮动。

对于因多加的代码`<div class="clear"></div>`而引起的高度变化，可以通过如下方法解决：
    clear {
         clear: both;
         height: 1px;
         margin-top: -1px;
         overflow: hidden;
    }

**方法二：使用:after清除浮动**

在CSS中关于:after（伪对象）的说明：设置在对象后发生的内容，通常和content配合使用，IE6、IE7不支持此伪对象。

常用的代码格式如下：
    .clearfix:after {
        content: "."; 
        display: block;
        height: 0px; 
        visibility: hidden;
        clear: both;
    }

首先设置display: block;，因为display的默认值是“inline”，不能收到clear的特性。同时将高度设为零（height: 0px;），可见度设为隐藏（visibility: hidden;）。

使用:after伪类清除浮动的优点是可以减少代码冗余，但在代码结构比较复杂或者清除浮动操作频繁的情况下，使用clear: both清除浮动是更好的选择。

**方法三：为父级盒子设置overflow: hidden**

首先，为什么加入overflow: hidden能实现清除浮动的效果呢？

如上文提到的，当元素设置了float浮动属性之后，它实际上就脱离了文档流。而我们对父级盒子设置overflow: hidden的作用就相当于是清除了父级在垂直于屏幕方向上的浮动，使父级回到文档流内。这样，父级盒子和子级盒子又重新处在一个层级之上。当我们没有给父级盒子设定长宽值的时候，子级盒子会撑开父级盒子，最终可显示的范围就是子级盒子的长宽值。这一情况解释了使用overflow: hidden清除浮动的原理。

在另一种情况下，如果我们给父级盒子设定一个具体的长宽值，那么无论子级盒子的长宽值是多少，最终显示的范围都是我们所设定的父级盒子的长宽值。这时，当子级盒子的范围超过父级盒子时，超出的部分就会被隐藏。这就是overflow: hidden隐藏溢出的含义的一个具体表现。



以上三种是各大浏览器兼容的清除浮动的方法。另外，这里提供一种不经常使用的方法仅供参考，符合条件的话可以灵活运用。

**补充方法：对父级设置适合的高度**

通过设置height属性的方法清除浮动，前提是父级内容高度要能够确定并计算好。



本文参考了以下资源：

[1] [CSS float属性](http://www.w3school.com.cn/cssref/pr_class_float.asp)

[2] [巧用clear: both](http://www.cnblogs.com/jenney-qiu/archive/2012/03/28/2421819.html)

[3] [全面阐述overflow: hidden属性](http://www.chinaz.com/design/2008/0818/35473.shtml)
