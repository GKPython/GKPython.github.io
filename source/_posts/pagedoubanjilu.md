---
title: 豆瓣自动获取个人记录
date: 2020-07-03 14:31:27
tags:  技术
---

想把豆瓣上自己的观影记录获取到本地，存在Excel中。

第一步：评估手工操作可行性，发现记录太多，不可行；

第二步：找寻网上有没有工具，结果发现大部分都被封了或者不能用。

然后，决定发扬自己动手，丰衣足食的作风，自己写一个，然后在网上随便找了一个例子，在此基础上开始。
1）编译，解决依赖；
2）编译通过，发现获取的网页内容为空，发现返回值418，被反爬了，然后通过增加header解决；
3）增加表格输出；
4）运行一切OK，输出效果如下图。

<div align=center>

![](/img/douban.png)

</div>