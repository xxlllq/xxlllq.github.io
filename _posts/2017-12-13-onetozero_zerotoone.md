---
layout: post
title:  "常见的0-1转换"
date:   2017-12-13
categories: "readme"
tags: [Other]
author: xxl
comment: false
---
利用程序将0变成1、1变成0，或者将1变成0、0变成1。

### 问题来源
<p style="text-indent: 2em">在项目中，很多时候都会对当前数据的状态做变更。比如说：如果当前数据是已审核状态，那么就变更为审核状态；如果当前数据是审核状态，那么就变更为未审核状态。究其根源就是0、1的切换。</p>
<p style="text-indent: 2em">这里我们主要介绍实现上述问题的四种方法：</p>

#### 方法一
<p style="text-indent: 2em">最初级、简单粗暴的方法就是<span style="font-weight:bold">if-else</span>，实现代码如下：</p>
{% highlight C# %}
if(number == 1) return 0;
else return 1;
{% endhighlight %}

#### 方法二
<p style="text-indent: 2em">初级+的方法就是<a href="https://baike.baidu.com/item/%E4%B8%89%E7%9B%AE%E8%BF%90%E7%AE%97%E7%AC%A6/6434591?fr=aladdin" target="_blank">三目运算符</a>，实现代码如下：</p>
{% highlight C# %}
number == 1 ? 0 : 1;
{% endhighlight %}

#### 方法三
<p style="text-indent: 2em">初级++的方法利用Math，实现代码如下：</p>
{% highlight C# %}
Math.(1 - number)
{% endhighlight %}

#### 方法四
<p style="text-indent: 2em">如果要展（kai）示（shi）技（zhuang）术（bi）的话，实现代码如下：</p>
{% highlight C# %}
Math.Cos(Math.PI * 1 / 2 * number)
{% endhighlight %}