---
layout: post
title: "简析id与class的区别及用法"
date: 2014-10-01 12:44:48 +0800
comments: true
categories: 
---
![Alt id&class](http://xubinbin.qiniudn.com/id%E4%B8%8Eclass%E5%AF%B9%E5%BA%94%E5%9B%BE.jpg
 "id与class对应图")

我们平常在用div+css制作网页时，常会用到id或者class来选择调用CSS样式属性。而就实现的页面效果而言，两者的视觉效果并无差别，那么我们什么时候该用id，什么时候又该用class，以及它们两者的命名规则和注意事项都有哪些呢？
<!--more-->

**命名和调用**

通常我们在CSS样式定义的时候，以“#”开头来命名id，以“.”开头来命名class；而在html结构中，以`<div id=""></div>`和`<div class=""></div>`的形式来进行调用。

注意：在命名id和class的时候要区分英文字母大小写，不要使用中文命名。

**id使用规则**

id具有唯一性，相同的id在同一个网页页面只能出现一次，并且一般在外围使用，因此网页的框架布局通常使用id，例如：logo、导航、主体内容、版权等，根据命名规范分别命名为#logo、#nav、#content、#copyright。

另外，在JS脚本中也会用到id，例如当JS要修改某一个标签的属性，以实现某种效果的时候，JS会将id作为该标签的唯一标识进行操作。这也是由id的唯一性决定的。

**class使用规则**

class在CSS定义中具有普遍性，相同的class在同一个网页页面可以无数次地调用，这体现了div+css布局的优越性。class常用于结构内部，通常是id的子级或者孙级，应避免出现class包含id的情况。



本文参考了以下资源：

[1] [CSS中的class与id区别及用法](http://www.divcss5.com/rumen/r3.shtml)

[2] [id和class的选择](http://www.codesky.net/article/201110/169389.html)
