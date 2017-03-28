---
title: Markdown基础
date: 2017-03-27 16:59:41
categories: "关于MarkDown"
tags: "MarkDown"
description: Markdown基础语法，刚接触、总结得不完善
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
![头图](http://ofopl9abq.bkt.clouddn.com/markdown.png)
</div>

>标题

    #一级标题
    ##二级标题
    ###三级标题

以此类推，总共六级标题，建议在井号后加一个空格，这是最标准的 Markdown 语法

>列表

熟悉 HTML 的同学肯定知道有序列表与无序列表的区别，在Markdown下，列表的显示只需要在文字前加上 - 或 * 即可变为无序列表，有序列表则直接在文字前加1. 2. 3.符号要和文字之间加上一个字符的空格。
- 一
- 二
- 三
1. 一
2. 二
3. 三

>引用

只需要在文本前加入 > 这种尖括号（大于号）即可
    >引用的内容

>图片与链接

插入链接与插入图片的语法很像，区别在一个 !号

    图片为：![](){ImgCap}{/ImgCap}

    链接为：[]()

插入图片的地址需要图床:
[google](http:www.google.com)

![iocn](http://ofopl9abq.bkt.clouddn.com/10.jpg?imageView2/2/w/100/q/50)

>粗体与斜体

Markdown 的粗体和斜体也非常简单，一段用两个 * 包含的文本就是的粗体语法，用一个 * 包含的文本就是斜体的语法。

example:**粗体** *斜体*

>代码块

要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：
这是一个普通段落：

    这是一个代码区块。

如果要标记一小段行内代码，你可以用反引号把它包起来（\`），例如：
`print()`