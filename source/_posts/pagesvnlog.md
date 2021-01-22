---
title: svn log修改
date: 2020-12-10 19:18:37
tags:
---

尴尬至极，发现自己昨天提交了一个svn日志“修改抬头纹贴”，想想好像是中午搜怎么修复额头上的川字纹，作为一个大老爷们，又是团队Leader，让组员看见了岂不是影响形象。
然后网上搜，说是可以在服务器端可以修改。但是根本没有界面。

<div align=center>

![](/img/svn-log.jpg)
</div>


然后想了一种办法，建立一个分支，把原先的分支删掉，但存在一个问题，一些提交历史消失。

最后呢，突然发现在服务器对应的仓库下面有一个hook，然后建立了pre-revprop-change.bat，运行一切OK。
if "%4" == "svn:log" exit 0 echo Property '%4' cannot be changed >&2 exit 1
