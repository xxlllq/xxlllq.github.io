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
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/new_report_cs.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/new_xtrareport.png"/></div>
### Filed List
<p style="text-indent: 2em">完成上述步骤后，对报表进行如下布局：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/table.png"/></div>
#### Add Data Binding
<p style="text-indent: 2em">至此我们就完成了报表的初步工作，接下来就是利用XtraReports中的Filed List为报表进行数据源绑定操作，具体的绑定步骤如下图片展示：</p>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/add_databinding.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/add_databinding.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/add_databinding.png"/></div>
<div style="text-align:center"><img height="auto" src="/assets/images/post/2017/2017-12-14-dev_wpf_xtrareport/add_databinding.png"/></div>