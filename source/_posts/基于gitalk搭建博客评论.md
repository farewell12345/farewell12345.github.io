---
title: 基于gitalk搭建博客评论
date: 2021-10-19 17:07:14
tags: blog
cover: https://i.loli.net/2021/10/22/Sc4foOw6jW7gCyG.png
---

# 起因

搭建好了个人博客，为了能够与沙雕网友在博客里愉快吹逼，需要开一个评论

<!--more-->

# 步骤

这里选用使用人数最多的[gitalk](https://github.com/gitalk/gitalk)

## 1. npm安装

```bash
npm i --save gitalk
```

## 2. 创建Github Application

创建一个GithubApplication，可以[点这里创建](https://github.com/settings/applications/new)

![](https://i.loli.net/2021/10/21/E13woviRhL8cdSH.png)

> **字段说明**：
>
> ​	Application name：应用名称,叫啥都行，可以叫BlogTalk方便区分
>
> ​	Homepage URL：你的博客的链接，如果没有配域名的话就是https://\<githubname>.github.io
>
> ​	Application description: 应用描述，随便写
>
> ​	Authorization callback URL:  验证回调地址，同HomePageURL

## 3. 查看clientID和clientSecret

到Github首页，点击个人头像->settings->Developer settings->OAuth Apps->刚才创建的应用

![](https://i.loli.net/2021/10/21/bBEZzhP5TvHpaxo.png)

![](https://i.loli.net/2021/10/21/StJjKEZe4DcmU7Q.png)

如图就是ClientID，点击Generate a new client secret可查看Client secrets

![](https://i.loli.net/2021/10/21/32ZzMywVvlUcXQ9.png)

## 4. 创建一个github仓库用来存储评论

随便新建一个仓库，注意设为Public即可

## 5. 配置

![](https://i.loli.net/2021/10/21/EjRYfImGpcwPdug.png)

找到博客主体的配置文件中关于gitalk的配置（如果博客没有可以参考[官方文档](https://github.com/gitalk/gitalk)，自己魔改一番）（如果不想改，建议换主题）

由此，gitalk便配置完成了，编译部署之后即可查看效果

# 番外：配置代理

在某些情况下可能会出现gitalk无法正常工作，报403、Netword Error等情况，这些情况只需要配置一个代理即可，解决方法可以参考[另一篇文章](https://farewell12345.github.io/2021/10/19/gitalk-403%E4%BB%A5%E5%8F%8AError-Validation-Failed%E9%97%AE%E9%A2%98%E8%A7%A3%E5%86%B3/)

