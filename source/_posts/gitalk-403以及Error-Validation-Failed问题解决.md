---
title: gitalk 403、Error_Validation_Failed以及Network Error问题解决
date: 2021-10-19 17:07:59
tags: [踩坑,blog]
cover: https://i.loli.net/2021/10/21/9fRcw8ajYz4WMTU.png
---

# 问题起源

在配置gitalk评论后，会出现403报错、Netword Error和Error_Validation_Failed等问题而导致gitalk无法正常使用,这些问题多半都是因为**缺乏gitalk代理**导致的

<!--more-->

![](https://i.loli.net/2021/10/21/9fRcw8ajYz4WMTU.png)

# 查找解决办法

先前往gitalk的github仓库看有没有人提issues，一番搜寻后发现确实有不少人有这个问题，而且已经给出了可能的原因

![](https://i.loli.net/2021/10/21/NUlaYjnCmKt2J3S.png)

前往博客查看接口响应情况

![](https://i.loli.net/2021/10/21/YiNMa5j2KdnHqAB.png)

确实如issues所说，国内无法正常访问github的access_token，按照issues提供的解决办法，来挂个代理试试

通过和[某位朋友](https://rainchan.win/)线下py,拿到了他自己搭建的一个代理地址

> 或者可以去别的网站打开F12寻找他们的access_token代理地址，比如[gitalk的官方网站](https://gitalk.github.io/)
>
> ![](https://i.loli.net/2021/10/21/HRJPQ8Ntix2EdFV.png)

然后去hexo主题源目录下找到gitalk的源文件（各个主题的文件路径可能不同，但是总可以找到的）

![](https://i.loli.net/2021/10/21/YFdWOxbtJple472.png)

修改gitalk对象构造器里的**proxy字段**（如果没有可以自己加一个）

最后编译，部署，问题便解决了

如果部署上去依然报错，那么多半是代理挂掉了，可以试试更换一个代理

