---
layout: post
title:  "DevExpress WPF汉化"
date:   2017-12-26
categories: "readme"
tags: [DevExpress, WPF]
author: xxl
comment: false
---
将DevExpress WPF的控件汉化。
### 引言
<p style="text-indent: 2em">几乎所有使用标准语言为zh-CN的WPF项目最终都会面临一个问题，那就是如何将WPF中的控件汉化，因为DevExpress额外只提供了de(German)、es(Spanish)、ja(Japanese)、ru(Russian)四种语言。除开这些语言之外的，要想实现控件语言自定义的就必须借助官网提供的语言包。</p>
### 实现
<p style="text-indent: 2em">DevExpress官网<a href="https://documentation.devexpress.com/WPF/7544/Localization/Localizing-WPF-Controls-via-Satellite-Resource-Assemblies" target="_blank">API</a>给出了实现控件语言自定义的方法，其中汉化必要的资源就是汉化包，其中<a href="https://localization.devexpress.com/" target="_blank">下载地址</a>，打开页面如下（需要DevExpress账号）：</p>
<div style="text-align:center"><img width="90%" height="auto" src="/assets/images/post/2017/2017-12-26-devexpress_localization_zh-CN/localization.png"/></div>
<p style="text-indent: 2em">图中显示的是测试时候下载的两个版本的汉化包（汉化包版本必须与电脑安装的Dev版本一致），图中表格会显示当前版本号、语言种类、总语句数、已翻译占比（包括WPF、WinForms、ASP.Net等产品），可通过<strong>Modify</strong>自定义翻译，如要下载新的语言包，可通过点击<strong>Add Translation</strong>，在弹出框选择适合自己当前Dev的版本号、标准语言，然后确认新增。</p>
<p style="text-indent: 2em">在完成语言包的编辑后，可通过勾选下载需要的版本。点击<strong>Download</strong>后，会提示你语言包正在准备，需要等待30分钟（实际上一两分钟）。完成之后，会向你登录邮箱发送一条下载链接，点击该链接会下载一个exe文件。</p>
<p style="text-indent: 2em">点击运行该exe文件，然后选择你需要放置语言包的地址，一般为项目的bin/Debug目录下面，然后点击<strong>Extract</strong>，等待完成后，改目录下面会多出一个文件，更改文件名为"zh-CN"。</p>
<p style="text-indent: 2em">以上就完成了汉化语言包的下载和放置于项目中，接下来就是在项目启动的时候加载语言包，具体的实现代码如下（App.xaml.cs）：</p>
{% highlight C# %}
public partial class App : Application
{
    public App()
    {
        this.Startup += Application_Startup;
    }
    private void Application_Startup(object sender, StartupEventArgs e)
    {
        CultureInfo culture =  CultureInfo.CreateSpecificCulture("zh-CN");

        Thread.CurrentThread.CurrentUICulture = culture;
        Thread.CurrentThread.CurrentCulture = culture;

        CultureInfo.DefaultThreadCurrentCulture = culture;
        CultureInfo.DefaultThreadCurrentUICulture = culture;
    }
}
{% endhighlight %} 