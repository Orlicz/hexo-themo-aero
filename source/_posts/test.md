---
title: 文章测试
date: 2022-08-11
categories:
  - system
  - test
comments: true
tags:
  - system
  - test
  - nullpost
---

- ## 前言
  `Hexo` 是一个快速、简洁且高效的博客框架。`Hexo` 使用 `Markdown`（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。即把用户的 `markdown` 文件，按照指定的主题解析成静态网页。

  <!--more-->

- ## 安装 `hexo`
  安装使用 `hexo` 之前需要先安装 `Node.js` 和 `Git`，当已经安装了 `Node.js` 和 `npm` (`npm` 是 `node.js` 的包管理工具)，可以通过以下命令安装 `hexo`

  ```shell
  $ npm install -g hexo-cli
  ```

  可以通过以下命令查看主机中是否安装了 `node.js` 和 `npm`

  ```shell
  $ node --version    #检查是否安装了node.js
  $ npm --version     #检查是否安装了npm
  ```

  如下所示表示已经安装了node.js和npm

  ```shell
  root@***:~# node --version
  v8.11.3
  root@***:~# npm --version
  6.7.0
  ```

- ## 建站
  安装完Hexo之后，执行下列命令，Hexo将会在指定目录中新建所需要的文件，指定的目录即为Hexo的工作站

  ```shell
  $ hexo init <folder>
  $ cd <folder>
  $ npm install
  ```

  新建完成之后，指定目录中的情况如下

  ```shell
  .
  ├── _config.yml
  ├── package.json
  ├── scaffolds
  ├── source
  |   ├── _drafts
  |   └── _posts
  └── themes
  ```

  - ### _config.yml
    网站的配置信息，您可以在此配置大部分的参数。 配置参数讲解

  - ### package.json
    应用程序的信息，以及需要安装的模块信息。

   - ### scaffolds
      模版文件夹。新建文章时，Hexo 会根据 scaffold 中的模板文件来建立新的文件。Hexo的模板是指在新建的markdown文件中默认填充的内容。例如，如果修改scaffold/post.md中的Front-matter内容，那么每次新建一篇文章时都会包含这个修改。也就是说，通过hexo命令每新建一个文章，都会包含指定模板文件中的内容。

      官网模板详述

    - ### source
      资源文件夹是存放用户资源的地方，如markdown文章。Markdown 和 HTML 文件会被解析并放到 public 文件夹，而其他文件会被拷贝过去。

      注意：除 _posts 文件夹之外，开头命名为 _ (下划线)的文件 / 文件夹和隐藏的文件将会被忽略。
    - ### themes
      主题文件夹。Hexo 会根据主题来解析source目录中的markdown文件生成静态页面。官网主题详述



- ## 写作
  可以执行下列命令来创建一篇新文章。
  
  ```shell
  $ hexo new [layout] <title>
  ```
  
  可以在命令中指定文章的布局（`layout`），不指定默认为 `post`，也可以通过修改 `_config.yml` 中的 `default_layout` 参数来指定默认布局。创建的新文章会自动加上指定布局对应的模板文件中的内容。

- ## 布局（Layout）
  Hexo 有三种默认布局：post、page 和 draft，它们分别对应不同的路径，而自定义的其他布局和 post 相同，都将储存到 source/_posts 文件夹。

  布局路径postsource/_postspagesourcedraftsource/_drafts

  如果你不想你的文章被处理，你可以将 Front-Matter 中的layout: 设为 false 。
- ## 模版（`Scaffold`）
  在新建文章时，Hexo 会根据 scaffolds 文件夹内相对应的文件来建立文件，例如：
 
  ```shell
  $ hexo new photo "My Gallery"
  ```
  
  在执行这行指令时，Hexo 会尝试在 scaffolds 文件夹中寻找 photo.md，并根据其内容建立文章，以下是您可以在模版中使用的变量：

  变量描述layout布局title标题date文件建立日期

- ## `Front-matter`

  `Front-matter` 是文件最上方以 `---` 分隔的区域，用于指定个别文件的变量，举例来说：
  
  ```yaml
  ---
  title: Hello World
  date: 2013/7/13 20:46:25
  ---
  ```
  
  注意：一般 `Front-matter` 使用的 `yaml` 语法，`yaml` 语法需要注意空格，如 `title: Hello World` 冒号需要有一个空格，当然除 `YAML` 外，你也可以使用 `JSON` 来编写 `Front-matter`。
  以下是预先定义的参数，您可在模板中使用这些参数值并加以利用。

  参数描述默认值 `layout` 布局 `title` 标题 `date` 建立日期文件建立日 `updated` 更新日期文件更新日期 `comments` 开启文章的评论功能 `truetags` 标签（不适用于分页） `categories` 分类（不适用于分页）`permalink` 覆盖文章网址



- ## 分类和标签

  只有文章支持分类和标签，您可以在 Front-matter 中设置。在其他系统中，分类和标签听起来很接近，但是在 Hexo 中两者有着明显的差别：分类具有顺序性和层次性而标签没有顺序和层次。

  ```shell
  categories:
  - Diary
  tags:
  - PS3
  - Games
  ```

  `WordPress` 支持对一篇文章设置多个分类，而且这些分类可以是同级的，也可以是父子分类。但是 `Hexo` 不支持指定多个同级分类。下面的指定方法： 
  ```shell
  categories:
    Diary
    Life
  ```
  
  会使分类 `Life` 成为 `Diary` 的子分类，而不是并列分类。因此，有必要为您的文章选择尽可能准确的分类.

- ## 文章摘要
  
  设置文章摘要，我们只需在想显示为摘要的内容之后添 `<!-- more -->` 即可。像下面这样：
