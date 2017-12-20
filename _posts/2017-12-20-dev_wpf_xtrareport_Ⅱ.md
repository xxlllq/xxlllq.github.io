---
layout: post
title:  "DevExpress WPF中的报表打印—Ⅱ"
date:   2017-12-20
categories: "readme"
tags: [WPF, C#, DevExpress]
author: xxl
comment: false
---
使用DevExpress WPF中的XtraReport进行数据打印。

### 引言
<p style="text-indent: 2em">其中<a href="https://xxlllq.github.io/readme/2017/12/14/dev_wpf_xtrareport_%E2%85%A0.html" target="_blank">DevExpress WPF中的报表打印—Ⅰ</a>已经介绍了最基本的报表打印功能的实现。本节将介绍新增临时字段（个人叫法）、对字段进行相关运算的实现，比如：两列之间的运算符操作。</p>
### 普通运算符
<p style="text-indent: 2em">首先我们将字段中的<strong>Length</strong>、<strong>Width</strong>、<strong>Thick</strong>相加，然后赋值给新的临时字段并显示在报表中：</p>
