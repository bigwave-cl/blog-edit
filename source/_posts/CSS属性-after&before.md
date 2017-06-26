---
title: CSS属性--after&before
date: 2017-06-26 11:43:46
categories: "关于CSS"
tags: "CSS"
description: 本文主要介绍after、before伪元素
---
### 伪元素after
{% blockquote MDN https://developer.mozilla.org/zh-CN/docs/Web/CSS/::after 关于After的描述 %}
CSS伪元素::after用来匹配已选中元素的一个虚拟的最后子元素。通常会配合content属性来为该元素添加装饰内容。这个虚拟元素默认是行内元素。
{% endblockquote %}

### 语法

```
element:after  { style properties }  /* CSS2 语法 */
element::after { style properties }  /* CSS3 语法 */
```

### 关于content

{% blockquote MDN https://developer.mozilla.org/zh-CN/docs/Web/CSS/content 关于Content的描述 %}
CSS的 content CSS 属性用于在元素的  ::before 和 ::after 伪元素中插入内容。使用content 属性插入的内容都是匿名的**[可替换元素](javascript:void)**。
{% endblockquote %}

上面提到了可替换元素，什么又是可替换元素呢？

{% blockquote MDN https://developer.mozilla.org/zh-CN/docs/Web/CSS/Replaced_element 可替换元素的定义 %}
CSS 里，可替换元素（replaced element）的展现不是由CSS来控制的。这些元素是一类 外观渲染独立于CSS的 外部对象。 典型的可替换元素有 `<img>`、 `<object>`、 `<video>` 和 表单元素，如`<textarea>`、 `<input>`。 某些元素只在一些特殊情况下表现为可替换元素，例如 `<audio>` 和 `<canvas>` 。 通过 CSS content 属性来插入的对象 被称作 匿名可替换元素（anonymous replaced elements）。

CSS在某些情况下会对可替换元素做特殊处理，比如计算外边距和一些auto值。

需要注意的是，一部分（并非全部）可替换元素，本身具有尺寸和基线（baseline），会被像vertical-align之类的一些 CSS 属性用到。
{% endblockquote %}

### content属性：
> 初始值: normal
> 适用元素: 所有伪元素
> 是否继承属性: 否
> 是否适用于CSS动画: 否

### content 取值：
**none**
　　不会产生伪类元素
**normal**
　　:before 和 :after 伪类元素中会被视为 none
**string**
　　文本内容
**url()**
　　URL值会指定一个外部资源（比如图片）。如果该资源或图片不能显示，它就会被忽略或显示一些占位（比如无图片标志）。
　　使用url()时空值、空字符串、不传递任何参数
>　　页面会渲染after伪元素，但是元素没有宽度，后台会请求当前域名，并请求成功

　　使用url()时错误的地址和不正确的参数
>　　页面会渲染after伪元素，但是元素没有宽度，后台会请求传递的错误地址和参数，并返回404错误

　　使用url()时正确的地址和参数
>   　页面会渲染after伪元素以及加载成功的资源，但是不能改变资源

**counter**
　　计数器可以指定两种不同的函数：counter() 或 counters()。前面一个有两种形式：counter(name) 或 counter(name,style) 。产生的内容是该伪类元素指定名称的最小范围的计数；格式由style指定（默认是'decimal'——十进制数字）。后一个函数同样也有两种形式：counters(name,string) 或 counters(name,string,style) 。The generated text is the value of all counters with the given name in scope at this pseudo-element, from outermost to innermost separated by the specified string. The counters are rendered in the indicated style ('decimal' by default). See the section on automatic counters and numbering for more information. The name must not be 'none', 'inherit' or 'initial'. Such a name causes the declaration to be ignored.
```--css--
body{
    counter-reset: tki tkl 5;
}
.test{
    color: green;
}
.test:before{
    content: '老子是大哥MAN';
    color: purple;
}
.test:after{
    counter-increment: tki +2 tkl -2;
    content: '计数器: ' counter(tki) '我不信：' counter(tkl);
    width: 100px;
    color: mediumvioletred;
}
```
```--html--
<div class="test">Here is a title!</div>
<div class="test">Here is a title!</div>
<div class="test">Here is a title!</div>
<div class="test">Here is a title!</div>
```
>　　这个东西需要counter-reset和counter-increment一起配合使用，目前我试了下好鸡儿神奇，但是好像只支持普通的加法和减法，乘法和除法不支持，他会在设定的初始值的基础上累加和累减

**attr(X)**
　　将元素的X属性以字符串形式返回。如果该元素没有 X 属性，则返回一个空字符串。区分大小写的属性返回值依赖文挡的语言设定。
>　　正如上面的定义，它会将元素的Ｘ属性以字符串的形式返回并正确渲染在指定的伪类元素上面

**open-quote | close-quote**
　　这些值会被 quotes 中定义的字符串替换。
```
.test2{
    color: green;
    quotes: "<<" ">>";
}
.test2:before{
    content:open-quote;
    color: purple;
}
.test2:after{
    content: close-quote;
    color: mediumvioletred;
}
```
>　　这玩意儿相当于可以在文档前后加上你想要的符号，ｓｏ　ｃｏｏｌ；

**no-open-quote | no-close-quote**
　　不会生产任何内容，但是会改变（增加或降低）引号层级。
>　　这个我没搞懂，希望有人不吝赐教

### 伪元素before

和after一致

### 总结
其实上面的内容都是从MDN上面搬过来的，我不是想要据为己有，而是记录在这里，表示我已经认真的看过after和before、以及content的属性值、默认值和传参错误时的表现。我希望我能在有限的时间内掌握的知识是一个比较全面的程度。


