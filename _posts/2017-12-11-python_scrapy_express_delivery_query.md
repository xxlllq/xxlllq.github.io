---
layout: post
title:  "Python爬虫获取物流运输路线"
date:   2017-12-11
categories: "readme"
tags: [Python]
author: xxl
comment: false
---
利用Python爬虫批量获取物流（快递EMS）订单列表的运输路线，源码可在<a href="https://github.com/xxlllq/python_scrapy_express" target="_blank">Github</a>查看。  

### Python
一直觉得爬虫技术很高大上，然后百度一番发现很多用<a href="https://www.python.org/" target="_blank">Python</a>写<a href="https://baike.baidu.com/item/%E7%BD%91%E7%BB%9C%E7%88%AC%E8%99%AB/5162711?fr=aladdin" target="_blank">爬虫</a>，自己以前也没有接触过Python，感觉这是一个学（zhuang）习（bi）的好机会。所以就用如下的测试数据开始了Python的爬虫学习，功能十分简单，代码丑陋： 
<div style="text-align:center"><img width="40%" height="auto" src="/assets/images/post/2017/2017-12-11-python_scrapy_express_delivery_query/express_data.png"/></div>
&nbsp;&nbsp;所谓爬虫，就像利用一只程序员赋予动态思维的“蜘蛛”，首先随机放置于一个网络节点，这只蜘蛛会获取该网络节点中程序认为有用的信息，并将这些有用信息通过相关规则提取出来，形成我们具体想要的数据。一般该网络节点还会有其他网络节点的链接，所以这只“蜘蛛”就会开始新数据找寻之旅，从而获取源源不断的数据。  
&nbsp;&nbsp;下面就介绍我们的利用Python爬虫抓取物流（快递）单号的运输路线，首先可用于查询快递的网站非常多，这里我利用<a href="http://www.kuaidi100.com/">快递100</a>

