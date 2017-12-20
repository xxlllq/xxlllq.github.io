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
<p style="text-indent: 2em">首先我们将字段中的Length、Width、Thick相加，然后赋值给新的临时字段并显示在报表中，具体的操作过程如下：</p>
<p style="text-indent: 2em">利用<strong>Field List</strong>中的<strong>Add Calculated Field</strong>新建一个临时字段，并通过<strong>Edit Calculated Fields</strong>将<strong>Name</strong>属性更改为TemTotal（可自定义），并将<strong>Field Type</strong>更改为Decimal（根据相互运算字段的类型）。</p>
<p style="text-indent: 2em">接下来就是最重要的一步，为临时字段编辑<strong>Expression</strong>，其中操作界面如下图：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/edit_expression_1.png"/></div>
<p style="text-indent: 2em">接下来就是最重要的一步，为临时字段编辑<strong>Expression</strong>在操作界面编写的如下表达式，点击OK：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/edit_expression_1.png"/></div>
<p style="text-indent: 2em">然后新增一列“长+宽+高”，并将TemTotal赋值给该列，同时新增该列的合计信息，最终的显示效果如下</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/print_result_1.png.png"/></div>