## 说明

本 Blog 基于 [@Huxpro](https://github.com/Huxpro/) 的 [Blog](https://github.com/Huxpro/huxpro.github.io) 修改，修改内容详见[修改内容](#修改内容)

## 目录

* [如何向Blog提交文章](#如何提交文章)
* [修改内容](#修改内容)
* [说明文档](#说明文档)
	* 开始
		* [环境要求](#environment)
		* [开始](#get-started)
		* [写一篇博文](#write-posts)
	* 组件
		* [侧边栏](#sidebar)
		* [迷你关于我](#mini-about-me)
		* [推荐标签](#featured-tags)
		* [好友链接](#friends)
	* 评论与 Google/Baidu Analytics
		* [评论](#comment)
		* [网站分析](#analytics) 
	* 高级部分
		* [自定义](#customization)
		* [标题底图](#header-image)
		* [搜索展示标题-头文件](#seo-title)
* [致谢](#致谢)



## 如何提交文章

打开 [https://github.com/cs1504/cs1504.github.io](https://github.com/cs1504/cs1504.github.io)

![create-new-file.png](https://i.loli.net/2018/03/09/5aa297685f20c.png)

点击 create new file 按钮，出现下面的页面。  
在这个页面中蓝色框框中说，你在一个你没有权限修改的项目里，因此，你复制了一份代码仓库到自己的账号上，你可以在自己的账号上进行修改，然后 commit，pull

![path-and-content.png](https://i.loli.net/2018/03/09/5aa297946009c.png)

提交完之后会出现下面的界面，可以在下面的界面中点击 create pull request 进行 pull 操作，即将自己修改后的代码向原始代码仓库提交

![create-pull-request.png](https://i.loli.net/2018/03/09/5aa29772a4c09.png)

之后会出现下面的页面，要求你填写 pull 的一些信息，以便告诉原始代码仓库的主人，你在这次修改中干了什么。

![open-a-pull-request.png](https://i.loli.net/2018/03/09/5aa297771cfb0.png)

这样操作之后你的代码就会提交到原始代码仓库中，之后等代码仓库的主人查看代码之后进行合并整理就可以了。

## 修改内容

0. 参考了 [@elmagnificogi](https://github.com/elmagnificogi/elmagnificogi.github.io) 的修改。
1. 删掉了一些对网页页面样式没有影响的代码。
2. 将大部分代码库引用改为 [BootCDN](http://www.bootcdn.cn/) 提供的加速服务。
3. 修改了 Jekyll 的插件等。

``` yml
plugins:
    - rouge             # 代码高亮插件
    - jekyll-paginate   # 分页插件
    - jekyll-sitemap    # sitemap 插件
    - jekyll-feed       # feed 插件
    - jemoji            # Emoji 表情插件

highlighter: rouge      # 高亮
markdown: kramdown      # markdown 
kramdown:
    input: GFM 
```

4. 将 comment 模块独立出来，并改为 Gitalk 。
5. 将 friends 模块独立出来，将 friends 的信息存储在 /_data/friends.yml 中。
6. 大部分内容改成了中文。
7. 修正了代码中一些小错误。

## 说明文档

* 开始
	* [环境要求](#environment)
	* [开始](#get-started)
	* [写一篇博文](#write-posts)
* 组件
	* [侧边栏](#sidebar)
	* [迷你关于我](#mini-about-me)
	* [推荐标签](#featured-tags)
	* [好友链接](#friends)
* 评论与 Google/Baidu Analytics
	* [评论](#comment)
	* [网站分析](#analytics) 
* 高级部分
	* [自定义](#customization)
	* [标题底图](#header-image)
	* [搜索展示标题-头文件](#seo-title)

#### Environment

如果你安装了jekyll，那你只需要在命令行输入`jekyll serve`就能在本地浏览器预览主题。你还可以输入`jekyll serve --watch`，这样可以边修改边自动运行修改后的文件。

经 [@BrucZhaoR](https://github.com/BruceZhaoR) 的测试，好像两个命令都是可以的自动运行修改后的文件的，刷新后可以实时预览。官方文件是建议安装bundler，这样你在本地的效果就跟在github上面是一样的。详情请见这里：https://help.github.com/articles/using-jekyll-with-pages/#installing-jekyll


#### Get Started

你可以通用修改 `_config.yml`文件来轻松的开始搭建自己的博客:

```
# Site settings
title: Hux Blog             # 你的博客网站标题
SEOTitle: Hux Blog			# 在后面会详细谈到
description: "Cool Blog"    # 随便说点，描述一下

# SNS settings      
github_username: huxpro     # 你的github账号
weibo_username: huxpro      # 你的微博账号，底部链接会自动更新的。

# Build settings
# paginate: 10              # 一页你准备放几篇文章
```

Jekyll官方网站还有很多的参数可以调，比如设置文章的链接形式...网址在这里：[Jekyll - Official Site](http://jekyllrb.com/) 中文版的在这里：[Jekyll中文](http://jekyllcn.com/).

#### write-posts

要发表的文章一般以 markdown 的格式放在这里`_posts/`，你只要看看这篇模板里的文章你就立刻明白该如何设置。

yaml 头文件长这样:

```yaml
---
layout: post
title: 'Hello 2015'
subtitle: 'Hello World, Hello Blog'
date: 2015-01-29 12:00:00
author: 'Hux'
header-img: 'img/post-bg-2015.jpg'
tags: [tag1, tag2]
---
```

#### SideBar

看右边:
![](https://huangxuan.me/img/blog-sidebar.jpg)

设置是在 `_config.yml` 文件里面的 `Sidebar settings` 那块。
```
# Sidebar settings
sidebar: true  #添加侧边栏
sidebar-about-description: "简单的描述一下你自己"
sidebar-avatar: /img/avatar-hux.jpg     #你的大头贴，请使用绝对地址.
```

侧边栏是响应式布局的，当屏幕尺寸小于992px的时候，侧边栏就会移动到底部。具体请见bootstrap栅格系统 <http://v3.bootcss.com/css/>


#### Mini About Me

Mini-About-Me 这个模块将在你的头像下面，展示你所有的社交账号。这个也是响应式布局，当屏幕变小时候，会将其移动到页面底部，只不过会稍微有点小变化，具体请看代码。

#### Featured Tags

看到这个网站 [Medium](http://medium.com) 的推荐标签非常的炫酷，所以我将他加了进来。
这个模块现在是独立的，可以呈现在所有页面，包括主页和发表的每一篇文章标题的头上。

```
# Featured Tags
featured-tags: true  
featured-condition-size: 1     # A tag will be featured if the size of it is more than this condition value
```

唯一需要注意的是 `featured-condition-size`: 如果一个标签的 SIZE，也就是使用该标签的文章数大于上面设定的条件值，这个标签就会在首页上被推荐。
 
内部有一个条件模板 `{% if tag[1].size > site.featured-condition-size %}` 是用来做筛选过滤的. 

#### Friends

好友链接部分。这会在全部页面显示。

设置是在 `/_data/friends.yml`文件里面

```
- title: "0xl2oot"
  href: "https://0xl2oot.cn/"
```

#### Comment

由于多说已经下架，别的也不怎么好用，所以采用 Gitalk 作为博客的评论系统。这里是我的设置，你应当去自己申请一个 ID。

```
comments_provider: gitalk
gitalk:
    owner: 0xl2oot
    repo: blog-comments
    clientID: f8e089a7e895625a0556
    clientSecret: 1f55fd61b1098ac55a8bf12f288cdbc6c43d9697
```

#### Analytics

网站分析，现在仅支持 Google Analytics。需要去官方网站注册一下，然后将返回的code贴在下面：

```yml
# Google Analytics
ga_track_id: 'UA-49627206-1'            # 你用Google账号去注册一个就会给你一个这样的id
ga_domain: huangxuan.me			# 默认的是 auto, 这里我是自定义了的域名，你如果没有自己的域名，需要改成auto。
```

#### Customization

**如果你可以理解 `_include/` 和 `_layouts/`文件夹下的代码（这里是整个界面布局的地方），你就可以使用 Jekyll 使用的模版引擎 [Liquid](https://github.com/Shopify/liquid/wiki) 的语法直接修改/添加代码，来进行更有创意的自定义界面啦！**

#### Header Image

标题底图是可以自己选的，看看几篇示例post你就知道如何设置了。在
  [issue #6 ](https://github.com/Huxpro/huxpro.github.io/issues/6) 中我被问到：怎么样才能让标题底图好看呢？
  
标题底图的选取完全是看个人的审美了，我也帮不了你。每一篇文章可以有不同的底图，你想放什么就放什么，最后宽度要够，大小不要太大，否则加载慢啊。

但是需要注意的是本模板的标题是**白色**的，所以背景色要设置为**灰色**或者**黑色**，总之深色系就对了。当然你还可以自定义修改字体颜色，总之，用github pages就是可以完全的个性定制自己的博客。

#### SEO Title

我的博客标题是 **“Hux Blog”** 但是我想要在搜索的时候显示 **“黄玄的博客 | Hux Blog”** ，这个就需要SEO Title来定义了。

其实这个SEO Title就是定义了<head><title>标题</title></head>这个里面的东西和多说分享的标题，你可以自行修改的。

## 致谢

1. 这个模板是从这里 [IronSummitMedia/startbootstrap-clean-blog-jekyll](https://github.com/IronSummitMedia/startbootstrap-clean-blog-jekyll)  fork 的。 感谢这个作者
2. 感谢 [@BrucZhaoR](https://github.com/BruceZhaoR) 的中文翻译 

3. 感谢 Jekyll、Github Pages 和 Bootstrap!