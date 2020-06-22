---
title: github page不能访问解决
date: 2020-06-22 10:16:58
tags: 技术
---

先说下不能访问前都干了些啥？
就一条操作：将page仓库从公有变成了私有，然后又从私有变成了公有，就不能访问了。

然后都做了些什么呢？
1 检查所有的配置，没有发现问题；
2 本地部署，hexo s，使用localhost：4000正常，不可以；
3 等待24小时，依然不可以。

进一步调查，有了新的发现：
1 GitHub Pages下没有Custom domain选项。

最终是怎么解决的呢？
1 点击Change theme
2点击 change theme 之后底下有个link-to-another-pages ，然后再选用主题就好了，这样可以跳转到你用hexo部署的界面
下面有两个主题1）默认的yay还有一个back，改成back
3 然后回来选项都有了，填上自己的域名，然后将Enforce HTTPS 也选上了。
再试一切OK。

