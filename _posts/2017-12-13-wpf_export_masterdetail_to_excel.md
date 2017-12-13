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
<p style="text-indent: 2em">只需要将上面代码中的<span style="color:#16c2c2;font-weight:bold;">DefaultFileName</span>替换成你想要的Excel文件名，其中<span style="color:#16c2c2;font-weight:bold;">MasterDetailDemo</span>为<span style="font-weight:bold;">TableView</span>的<span style="font-weight:bold">Name</span>属性值。</p>

### PrintHelper
<p>上面代码已经实现了最常见的DataGrid导出到Excel，但有些时候我们需要将MasterDetail及所属子级详情导出至Excel，这时候可能就需要用到<span style="font-weight:bold">PrintHelper</span>，这时候只需引用DevExpress.Xpf.Printing，然后需要为<span style="font-weight:bold">TableView</span>添加<span style="color:#16c2c2;font-weight:bold;">PrintAllDetails</span>属性，并将上述代码更改成如下：</p>
{% highlight C# %}
using DevExpress.Xpf.Printing

if (saveFileDialogService.ShowDialog())
{
    var fileName = saveFileDialogService.GetFullFileName();
    var tableView = ((TableView)MaterielPurchaseGrid.View); 
    tableView.PrintAutoWidth = false; 
    PrintHelper.ExportToXlsx(tableView, fileName,
                            new XlsxExportOptions() {
								ShowGridLines = true, 
							}); 
    if (DXMessageBox.Show("是否打开导出文件？", "系统提示",
                         MessageBoxButton.OKCancel, MessageBoxImage.Information) == MessageBoxResult.OK)
        Process.Start(fileName);
}
{% endhighlight %} 
<p style="text-indent: 2em">其中的<span style="font-weight:bold">TableView</span>如下:
{% highlight C# %}
 <dxg:TableView Name="MasterDetailDemo" PrintAllDetails="True"></dxg:GridControl.View>
{% endhighlight %} 