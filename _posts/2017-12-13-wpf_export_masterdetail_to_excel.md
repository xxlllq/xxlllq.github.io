---
layout: post
title:  "WPF导出MasterDetail及所属子级详情至Excel"
date:   2017-12-11
categories: "readme"
tags: [WPF, C#, DevExpress]
author: xxl
comment: false
---
利用PrintHelper将WPF中的MasterDetail及所属子级详情导出至Excel。

### TableView
<p style="text-indent: 2em">WPF的DataGrid导出Excel到指定文件夹很简单，直接利用如下代码即可实现功能。</p>
{% highlight C# %}
using System.Diagnostics;
using System.Windows;
using DevExpress.Mvvm;
using DevExpress.Mvvm.UI;
using DevExpress.Xpf.Core;
using DevExpress.Xpf.Grid;  

SaveFileDialogService saveFileDialogService = new SaveFileDialogService()
{
    DefaultExt = "xls",
    Filter = "Excel 2007+|*.xls",
    DefaultFileName = "You_Want_Excel_Name"
};
if (saveFileDialogService.ShowDialog())
{
    var fileName = saveFileDialogService.GetFullFileName();
    (MasterDetailDemo.View as TableView).ExportToXls(fileName);
    if (DXMessageBox.Show("是否打开导出文件？", "系统提示", 
                         MessageBoxButton.OKCancel, MessageBoxImage.Information)
                         == MessageBoxResult.OK)
        Process.Start(fileName);
}
{% endhighlight %}
<p style="text-indent: 2em">只需要将上面的DefaultFileName替换成你想要的Excel文件名，MasterDetailDemo为TableView的Name属性值。</p>

### PrintHelper

<p>需要引用DevExpress.Xpf.Printing</p>
{% highlight C# %}
 <dxg:TableView Name="MasterDetailDemo" PrintAllDetails="True"></dxg:GridControl.View>
{% endhighlight %} 