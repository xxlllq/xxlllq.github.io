---
layout: post
title:  "使用Linq筛选满足数组条件的List集合"
date:   2017-12-09
categories: "readme"
tags: [Linq, C#]
author: xxl
comment: false
---
使用Linq从List中删选出满足指定条件的元素，其中条件为：给定任意数组（string、与List元素同维数），只要List中的元素包含数组中给定元素，则认为此List的元素符合条件。

几周前在做项目的时候，需要实现一个功能：利用“长\*宽\*高”的这种形式搜索数据。需要达到的效果就是输入“num1\*num2\*num3”，其中num1、num2、num3的组合不确定，简单来说就是“num1\*num2\*num3”需要匹配“长\*宽\*高”、“长\*高\*款”、“宽\*长\*高”，……，等6种组合。

## 案例
{% highlight C# %}
 List<Size> strList = new List<Size>();
 strList.Add(new Size { L = "225.00", W = "170.00", T = "38.00" });
 strList.Add(new Size { L = "505.00", W = "158.00", T = "162.00" });
 strList.Add(new Size { L = "480.00", W = "340.00", T = "130.00" });
 strList.Add(new Size { L = "163.00", W = "3.00", T = "406.00" });
 strList.Add(new Size { L = "54.00", W = "23.00", T = "41.00" });
{% endhighlight %}
 
### 情景一

用来比较的数组：
{% highlight C# %}
 {"1","3","4"} or {"1","4","3"} or {"3","1","4"} or {"3","4","1"} or {"4","1","3"} or {"4","3","1"}
{% endhighlight %} 
使用方法比较后，结果为：
{% highlight C# %}
[{"163.00""3.00","406.00"},{"480.00","340.00","130.00"}]
{% endhighlight %}

* 情景二

用来比较的数组：
{% highlight C# %}
 {"1","","4"} or  {"4","","1"} or  {"","1","4"} or  {"","4","1"} or  {"1","4",""} or  {"4","1",""}
{% endhighlight %} 
使用方法比较后，结果为：
{% highlight C# %}
[{"163.00""3.00","406.00"},{"480.00","340.00","130.00"}]
{% endhighlight %}

* 情景三

用来比较的数组：
{% highlight C# %}
 {"1","",""} or  {"","1",""} or  {"","","1"} 
{% endhighlight %} 
使用方法比较后，结果为：
{% highlight C# %}
[{"225.00","170.00","38.00},{"505.00","158.00","162.00"},
 {"163.00""3.00","406.00"},{"480.00","340.00","130.00"}]
{% endhighlight %}

#### Class Is
{% highlight C# %}
public class Size
{
  public string L { get; set; }
  public string W { get; set; }
  public string T { get; set; }
}
{% endhighlight %}



Github地址传送门  [使用Linq筛选满足数组条件的List集合]

[使用Linq筛选满足数组条件的List集合]: https://github.com/xxlllq/Linq_List_Contrast_Baseon_Array
