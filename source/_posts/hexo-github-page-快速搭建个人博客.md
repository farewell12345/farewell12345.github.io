---
title: Hexo + github Page 快速搭建个人博客
date: 2021-04-12 20:13:23
tags: Hexo
cover: https://i.loli.net/2021/04/12/DaEkMR9SNBKFfV8.png
mathjax: true
---

使用Hexo+Github Page快速搭建个人博客 

<!--more-->

**注意：本博客仅仅针对纯小白，快速搭建一个能用的博客**

# 环境搭建

1. 安装[NodeJS](http://nodejs.cn/learn/how-to-install-nodejs)(建议使用 Node.js 12.0 及以上版本)

2. 安装[Git](https://www.liaoxuefeng.com/wiki/896043488029600/896067074338496)（参考廖雪峰git教程）

3. 注册一个Github账号

4. 登录Github

5. 在GitHub上新建一个仓库

   ![](https://i.loli.net/2021/04/12/altbZHiUjze6r73.png)

   > 如图，点击**New repository**，在**Repository name** 的位置填写域名，格式是 **username.github.io**.
   >
   > 比如你的github名字是farewell12345，那么这里就写farewell12345.github.io

   <img src="https://i.loli.net/2021/04/12/TB6rNASgf49kPIy.png" style="zoom:67%;" />

   > 填完以后可以啥都不用选，拉到最下面**点击Create repository**
   >
   > 创建成功之后，进入仓库，点击右上角的 Settings

   ![](https://i.loli.net/2021/04/12/FJ9Dl2BVkEdSKMu.png)

   > 找到 GitHub Pages 选项，选择一个 GitHub 官方提供的主题

   ![img](https://cdn.sspai.com/20190506142607.jpg)

   > 主题随便选一个，选择完毕后在跳转界面点击Commit changes，就完成了Github Page的配置
   >
   > 这时可以试着访问一下 **https://username.github.io**   （就是刚才在**Repository name** 的位置填写的域名），如果正常打开了页面，就说明配置成功了。

6. > **选择一个空文件夹**，打开Bash窗口（装好Git以后右键菜单中自带），使用npm安装Hexo

   ```bash
   npm install hexo-cli -g
   ```

   > 安装完成后依次执行下列命令

   ```bash
   hexo init Blog
   cd Blog
   npm install
   hexo g
   hexo s
   ```

   > hexo s输入完毕后，不要关闭Bash窗口,就保持这样的状态，然后进入浏览器，输入http://localhost:4000，去尝试访问这个地址，如果访问到了页面，说明本地Hexo 环境已经搭建好了

   ![](https://i.loli.net/2021/04/12/khg9cIexFs4X6a7.png)

# 开始搭建属于自己的博客

> 到[Hexo主题网站（点击蓝字即可）](https://hexo.io/themes/index.html)找一个你最顺眼的主题，点进去，找到它的使用手册，因为不同的主题其说明文档也不一样，所以在配置主题的过程中就需要自己去踩坑了。这里以我目前在用的[Nexmoe主题](https://github.com/theme-nexmoe/hexo-theme-nexmoe)为例：
>
> 从Hexo主题网站找到它以后，点击进入它的Github仓库，点击Code，然后download zip（如果配置了Git SSH Key可以选择直接clone），下载主题。

![](https://i.loli.net/2021/04/12/UoNKeZAJabO1E8Y.png)

> 打开你电脑上之前用Hexo生成的Blog文件夹,进入themes文件夹中，把刚才下载好的主题zip**解压并放入这个themes文件夹下**

![](https://i.loli.net/2021/04/12/9SWjfnUIdHOK1Xb.png)

​			![](https://i.loli.net/2021/04/12/NaRAJjgOYZemrPT.png)

> 打开blog目录下的config.yml配置文件，修改theme为主题文件夹的名字，比如：

![](https://i.loli.net/2021/04/12/alC1nNsSvrdEwxp.png)

> 在config.yml中修改博客名和描述等信息

![](https://i.loli.net/2021/04/12/YUftQ2PCTZ53NBw.png)

![](https://i.loli.net/2021/04/12/CN4upV1bPYU8Dqy.png)

> author:作者
>
> title：你博客标题（名字）
>
> description：博客描述
>
> url：设置你博客的域名（就刚才在Github上设置的那个）
>
> config基础设置这样就可以了，其他如果想了解的话可以去[Hexo官方文档](https://hexo.io/zh-cn/docs/)

> **返回主题仓库查看Readme**

![](https://i.loli.net/2021/04/12/JT42NABOcyjuQlH.png)

> 查看主题的教程，对主题进行自定义配置
>
> 打开主题文件夹

![](https://i.loli.net/2021/04/12/EYSJrR94QegWm8A.png)

打开这个目录下的config.yml，对照主题官方文档进行自定义配置

（因为每个人选择的主题不一样，所以这里就不多赘述了，一般主题的官方文档是写得很详细的）

### 运行博客

在Blog根目录下运行Bash窗口，输入

```bash
hexo g
hexo s
```

访问http://localhost:4000就可以看到自己配置出的博客了（如果步骤没有错误的话）

输入

```bash
hexo s --debug
```

可以进入debug模式，可以看到博客的运行日志

### 部署博客

进入Blog目录下的public文件夹，打开Bash窗口，依次输入以下命令：

```bash
git init
git remote add origin  <你的博客在github上的链接>
git add .
git commit -m "提交的描述"
git push origin master
```

这里需要获取**你的博客在github上的链接**，打开博客对应的github仓库，点击code，

![](https://i.loli.net/2021/04/12/Pdqr9t3ZfGAo6TC.png)

这个就是仓库的链接

push成功以后，等一会去查看github仓库是否有了我们push上去的东西，如果有，那就可以去试着访问https://username.github.io（就是刚才在**Repository name** 的位置填写的域名）了，如果出现了界面，那就说明博客成功了

![](https://i.loli.net/2021/04/12/xvni69PqEBIQg8a.png)

<h4>如果配置的过程中遇到未知错误，请记住搜索引擎是个好东西（</h4>