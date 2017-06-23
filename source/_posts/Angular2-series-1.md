---
title: Angular2（一）
date: 2017-03-29 10:43:27
categories: "关于Angular2"
tags: "Angular2"
description: 本文主要介绍Angular-Cli的相关配置和基础用法
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
![头图](http://ofopl9abq.bkt.clouddn.com/angular2.png)
</div>

前言
====
-------------

本文所有内容均是参考大漠穷秋老师的[Angular2.0视频教程](http://www.bilibili.com/video/av8700148/?from=search&seid=1544907794104278646),你可以点击上方链接快速进入视频教程版，下面的内容纯粹只是个人记录，怕自己忘了。

-------------------------------------------------------------------------------

一
====

使用 `npm install -g angular-cli` 安装angular-cli
**PS:** 这里大漠穷秋老师推荐使用cnpm安装

[angular-cli](https://www.npmjs.com/package/angular-cli)它集成了很多工具，比如：karma、webpack、typescript等等

二
====

1.使用 `ng new 项目名称` 初始化一个项目;
2.项目初始化完成后**切换**到**项目文件目录**;
3.在**项目目录**下使用 `npm isntall`（`cnpm`也行） 安装package.json文件中的依赖
4.等待安装完成

三
====

使用 `ng server` 启动项目

**PS:** 使用 `ng server --prod --aot` 可以简化项目（他会压缩代码并去除掉你没有使用到的module）

ng generate
====

![ss](/plates/angular2_1_1.png)

上面的插图对应 `ng generate` 的命令，而且所有的命令均支持简写 `ng g`

**Example：** 
>`c:component` 可以这样用 `ng generate component 名称` 也可以简写 `ng g c 名称`

ng build
====
使用`ng build`或者`ng build --prod --aot`构建项目，他会在当前项目的根目录下面生成一个dist文件夹，里面有你想要的东西

ng test
====
使用`ng test`启动单元测试用例

-----------------------------------------------
over