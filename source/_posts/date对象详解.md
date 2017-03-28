---
title: Date对象在各种浏览器的爱恨情仇
date: 2017-03-28 10:46:37
categories: "关于JavaScript"
tags: "JavaScript"
description: 本文主要介绍Date对象在各种浏览器下传参的不同会出现的问题、以及最后的解决方案
---
<style type="text/css">
    .no-border{
        text-align: center;
    }
    .no-border img{
        border:none !important;
        margin: 0 auto !important;
    }
</style>

<div class="no-border">
![头图](http://ofopl9abq.bkt.clouddn.com/javascript.png)
</div>

>前言

在前端开发中难免会和Date对象谈恋爱，可是彼此之间的接触又不够深入以至于都不了解对方就开始胡乱“插入”对方的生活。起初还好，随着时间的推移突然发现大家都有很想法不一样的地方，但是大家都以自己认为对方合适的方法处理问题，所以出现了一些列乌龙事件。

>Date()

我们创建Date对象用来处理日期和时间，Date对象基于1970年1月1日起的毫秒数。
它支持的初始化方式如下：

    new Date();
    new Date(value);
    new Date(dateString);
    new Date(year, month[, day[, hour[, minutes[, seconds[, milliseconds]]]]]);

当Date作为构造函数调用并传入多个参数时，如果数值大于合理范围时（如月份为13或者分钟数为70），相邻的数值会被调整。比如 new Date(2017, 13, 1)等于new Date(2018, 1, 1)，它们都表示日期2018-02-01（注意月份是从0开始的）。其他数值也是类似，new Date(2017, 2, 1, 0, 70)等于new Date(2017, 2, 1, 1, 10)，都表示时间2017-03-01T01:10:00。

>浏览器表现

当传递的参数为dateString的时候在各个浏览解析的情况：

    var t = new Date(dateString);
    console.log(t);


[各浏览表现的情况，请戳我](http://dygraphs.com/date-formats.html)

>解决方法

相信到这里大家心里面都有自己的想法了
1. 使用`new Date(dateString);`，请注意不要使用'yyy-m-d hh:mm:ss'这种格式，毕竟它不兼容所有浏览器。当然还要其他的情况，请参照上面的兼容表格；
2. 使用`new Date(year, month[, day[, hour[, minutes[, seconds[, milliseconds]]]]]);`，它是兼容所有浏览器的

>总结

要想过好每一天我们需要相互了解。

>参考网址

[MDN关于Date的详细介绍](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date)

