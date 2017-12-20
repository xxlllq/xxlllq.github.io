---
layout: post
title:  "DevExpress WPF中的报表打印—"
date:   2017-12-14
categories: "readme"
tags: [WPF, C#, DevExpress]
author: xxl
comment: false
---
使用DevExpress WPF中的XtraReport进行数据打印。

### 新建项目
<p style="text-indent: 2em">在VS2015中，创建如下结构的WPF项目：<a href="https://github.com/xxlllq/Dev_Wpf_XtraReport" target="_blank">Github源码</a></p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/devwpfxtrareport.png"/></div>
<p style="text-indent: 2em">其中<span style="color:#16c2c2;font-weight:bold;">XtraReportDemo</span>文件按照如下方式新建，个人习惯直接创建Empty模板：</p>
<div style="text-align:center;display:inline">
<img width="45%" height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/new_report_cs.png" style="margin-right:10px"/>
<img width="45%" height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/new_xtrareport.png"/>
</div>
### Filed List
<p style="text-indent: 2em">完成上述步骤后，对报表进行如下布局：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/table.png"/></div>
#### Add Data Binding
<p style="text-indent: 2em">至此我们就完成了报表的初步工作，接下来就为报表进行数据源绑定，具体的绑定步骤如下图片展示：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/add_databinding.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/data_souce_wizard.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/select_viewmodel.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/view_item_source.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/retrieve_the.png"/></div>
<p style="text-indent: 2em">点击<strong>Finsh</strong>完成数据绑定。</p>
<p style="text-indent: 2em">完成数据源绑定后，调出Field List如下图所示：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/field_list.png"/></div>
<p style="text-indent: 2em">然后拖过直接拖拽完成字段与字段显示位置的对应，其中：可对<strong>Date</strong>字段进行格式化，具体格式化操作如下图所示：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/date_format.png"/></div>
<p style="text-indent: 2em">如果几个字段需要显示在同一个单元格内，此时需要将几个字段绑定到<strong>Text</strong>上面，具体格式化操作如下图所示（其中的<strong>*</strong>为连接字符，可以自定义）：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/binding_LWT.png"/></div>
<p style="text-indent: 2em">如果需要对相关字段进行统计计算，可按照下面步骤进行相关操作（示例中统计字段为<strong>Length</strong>）：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/sum_length.png"/></div>
### 效果
<p style="text-indent: 2em">最终完成的效果如下：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/print_result.png"/></div>