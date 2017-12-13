---
layout: post
title:  "常见的0、1转换"
date:   2017-12-13
categories: "readme"
tags: [Other]
author: xxl
comment: false
---
利用程序将0变成1、1变成0；将1变成0、0变成1。

### 问题来源
<p style="text-indent: 2em">在项目中，很多时候都会对当前数据的状态做变更。比如说：如果当前数据是已审核状态，那么就变更为审核状态；如果当前数据是审核状态，那么就变更为未审核状态。究其根源就是0、1的切换。</p>
<p style="text-indent: 2em">这里我们主要介绍第二个问题，因为对于第一个问题，也就是“将0变成1、1变成0”，我们直接就利用<span style="font-weight:bold">【1-number】</span>就搞定了。下面就介绍第二个问题的四种方法：</p>

#### 方法一
<p style="text-indent: 2em">最简单粗暴的方法就是<span style="font-weight:bold">c</span>，实现代码如下：</p>
{% highlight C# %}
var result = OneToZeroAndZeroToOne(1);

//Function()
public int OneToZeroAndZeroToOne(int number)
{
  return 1-number;
}
if(number == 1) 
{% endhighlight %}