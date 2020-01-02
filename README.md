Ben Campagna
This is the source code for BenCampagna.com, a Jekyll-powered website.

LOFFER is software that can help you get off from LOFTER (I know this pun sucks).

This is a Jekyll blog that can be published directly on GitHub through Fork. You don't need to write code or use the command line to get a blog deployed on GitHub.

update content
2019-07-25 V0.4.0
The problem that the revision directory jump will be broken is not a perfect solution, but it will not be broken.

Added support for LaTeX rendering, see this description and example.

Add the pinning function, as long as you add pinned: true to the YAML Front Matter of the post (the piece of information in the head of the article), this article can be pinned.

In addition, a method of changing the theme color for LOFFER is introduced. LOFFER uses an open source color table, Open Color. The available colors are: red, pink, grape, violet, indigo, blue, cyan, teal, green, lime, yellow.

The default state of LOFFER is teal. To change the theme color, just open the file _sass / _variables.scss and replace all teal in the file with the color you want. For example, find teal, replace indigo, replace all, commit, and finish!

2019-07-20 V0.3.0
The new version adds a directory function. Add toc: true to the post's information center, and this blog post will display the directory.

There is no modification to config this time, so you should be able to update it by submitting a pull request to yourself through this method.

The catalog is based on jekyll-toc by allejo.

At the moment I tried it and found a small problem: if your title level does not change according to the routine, it will not understand ...

Below the first-level title must be ## second-level title, if it is ### third-level title, it will be artificially retarded [manual support amount]

Note: Currently the catalog is only displayed on the desktop version.

2019-06-30 V0.2.0
The new version further optimizes the style and supports Gitalk based on GitHub Issues (see the configuration instructions below).

If you have forked LOFFER and want to update to a new version, you can try this method, or you can simply delete it again, as long as you keep most of your config settings and all posts.

LOFFER is just a container. Your posts are the core of your blog.

note
LOFFER is a blog template. There is no problem publishing personal blogs using GitHub Pages. but:

Do not post adult-oriented content
Don't upload a lot of images to GitHub
If in doubt, read the official GitHub Pages instructions.

In addition, the better publishing platform for fanart works is AO3. Do you think you posted on AO3, there are tags, kudos, and people watch, right?

how to use
First of all, this blog theme is suitable for mobile reading, but to use it to build your own blog, you need to operate on a computer.

Step 1 Fork to your GitHub
Please click on GitHub to sign up for a GitHub account. We can understand that Git is a file version management system, and does not need to know the code to use it.

The LOFFER you see now exists as a Repository (code repository) on GitHub. You can copy this code repository to your own GitHub account. This operation is called Fork.

Click LOFFER, go to LOFFER's GitHub Repository page, and then click Fork:

gif

Then you can immediately see LOFFER appear again, this time it already belongs to you. Here I suggest you rename it, click settings, and give your blog a name (please use letters instead of Chinese if possible).

img

Then, pull down the page, you will see "GitHub Pages", which is the built-in website host service of GitHub, select master, as shown in the figure:

img

After a few seconds, refresh this page, you usually see this green thing (if you do n’t see it, wait a while), your website has been successfully published, click this link to view:

img

You may see the site looks ugly, please continue to the next step.

Step 2 Set site information
On your blog's GitHub codebase page, select Code, select _config.yml from the file list, click Open, and click the pen icon in the upper right corner to modify the document.

After making changes, click "Commit changes". Every time you modify the code base and commit, GitHub Pages will automatically republish the website. Just wait a few minutes and refresh your blog page again to see your changes.

Another point is that LOFFER uses the MIT protocol, which means that all open source is free to use. If you want to retain your rights to blog posts, please edit the LICENSE file and write something like "Document authors in _posts reserve rights".

Step three
On your blog's GitHub codebase page, open the _posts folder, which is your blog post.

The format of these articles is Markdown, and the file extension is md. This is a very simple and easy to use formatted text markup language. You should have noticed that there is a Chinese Markdown syntax in the example blog that comes with LOFFER. Introduction.

The easier way is to use Typora, which is a fully graphical interface and full real-time preview of Markdown writing software. It is very lightweight and free.

img

Before posting a blog post, you need to add such content to the head of the article, including your article title, publication date, author name, and tag.

---
layout: post
title: LOFFER Document
date: 2019-06-02
Author: From China World
categories:
tags: [sample, document]
comments: true
---
After completion, save as a .md file with the file name as date-title, such as 2019-06-02-document.md (note that the title here will become the URL of this post, so it is recommended to use letters instead of Chinese, it does not affect the page Title shown above), and then upload it to the _posts folder, commit, and soon you can see the new post on the blog.

Optional: What about pictures?
A small number of images can be uploaded to the images folder and then added to the blog post.

However, GitHub is used as a map bed, which is suspected of abuse. If your blog is based on pictures, it is recommended to choose an external map bed, for example sm.ms is a good choice.

If you want to find a chart bed that suits you better, please Google it.

The markdown syntax for adding pictures to a blog post is:! [Picture name] (URL)

Optional: Add a comment area
Disqus
LOFFER supports Disqus comments. Although Disqus is ugly, it is free and easy to set up, so don't dislike it.

First, sign up for a Disqus account and we can choose this free plan:

img

After the registration is successful, create a new site (site). Take LOFFER as an example. The setting steps are as follows:

First of all, the site name is LOFFER, and the shortname is loffer. The type can be chosen at will.

img

Select Jekyll during installation.

img

Finally, fill in your blog address, the language can choose Chinese, click Complete, you can!

img

Then you need to return to your blog, modify the _config.yml file, fill in your shortname, commit in thequs field, and you are done!

Gitalk
New content, LOFFER 0.2.0 version supports Gitalk comment area (still in the LOFFER sample station is Disqus, you can view Gitalk demo on my blog), the setting method is as follows:

First, create an OAuth application, set up as shown:

img

After clicking Register, you will see the two values ​​you need, clientID and clientSecret. Copy them to the corresponding fields in your _config.yml file:

gitalk:
  clientID: <your clientID>
  clientSecret: <your clientSecret>
  repo: <your repository name>
  owner: <your GitHub username>
Then commit and your Gitalk comment area will appear. For each article, you need to enter the article page to initialize the comment area. This operation will create an Issue on your repository, and subsequent comments will be a reply to this Issue.

You can go to the Issue page of your repository and click Unsubscribe to avoid receiving a lot of relevant emails.

Note: For obvious reasons, it's best not to add both Disqus and Gitalk comment sections.

Import LOFTER content
This is partly due to the excellent export file of LOFTER, which needs to be solved separately.

You can use the script of asking the non-named wife, and choose Jekyll to output.

I'm personally tossing a script. I haven't fully debugged it yet. In any case, please export it in lofter first. It is also good to have a local. Post it can make all the content disappear before 2017. China Internet, nothing is impossible .

Thanks
Jekyll-This is the foundation of this site
Kiko-now-I first fork this theme, and then modified and localized it before I got LOFFER
Font Awesome-social network icon from FontAwesome free open source content
Help this project
Introduce more people to use it and fly free from lofter!

Of course, if you just write the same person, I still recommend that everyone go to AO3, but their own blog is also very cool, you can also choose many other forkable Jeykll themes, there are many on GitHub, or try other blog building tools Hexo, for example, has a lot of fun with code.

Finally, back to LOFFER(https://github.com/FromEndWorld/LOFFER), give me some ☆!

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/givemefive.png)

LOFFER是个可以帮助你get off from LOFTER的软件（我知道这个pun很烂）。

这是一个可以通过Fork直接发布在GitHub的Jekyll博客，你不需要编写代码或使用命令行即可获得一个部署在GitHub的博客。

## 更新内容

### 2019-07-25 V0.4.0

修订目录跳级会坏掉的问题，不算完美解决，但不会坏掉了。

增加对LaTeX渲染的支持，请见[这篇说明和示例](https://fromendworld.github.io/LOFFER/math-test/)。

增加置顶功能，只要在一个post的YAML Front Matter（就是文章头部的这段信息）中加入` pinned: true `，这篇文章就可以置顶了。

另外介绍一个给LOFFER更换主题颜色的手法。LOFFER用了一个开源的颜色表[Open Color](https://yeun.github.io/open-color/),该色表提供的可选颜色有：red, pink, grape, violet, indigo, blue, cyan, teal, green, lime, yellow。

LOFFER的默认状态是teal，要更换主题颜色，只要打开文件` _sass/_variables.scss `，将文件中所有的teal全部替换成你想要的颜色。例如，查找teal，替换indigo，全部替换，commit，完成！


### 2019-07-20 V0.3.0

新版本增加目录功能，在post的信息中心加入` toc: true `，这篇博文就会显示目录了。

这次没有对config的修改，因此应该可以通过[这个方法](https://github.com/KirstieJane/STEMMRoleModels/wiki/Syncing-your-fork-to-the-original-repository-via-the-browser)，给自己提pull request来更新。

目录基于[jekyll-toc by allejo](https://github.com/allejo/jekyll-toc)制作。

目前我试用发现了一点小问题：如果你的标题级数不按套路变化，它就会搞不懂…… 

` # 一级标题 `下面必须是` ## 二级标题 `，如果是` ### 三级标题 `它就人工智障了【手动扶额】

注意：目前目录仅在桌面版显示。


### 2019-06-30 V0.2.0

新版本进一步优化了一下样式，并且支持了基于GitHub Issues的评论Gitalk（请看下文的配置说明）。

如果你已经fork了LOFFER，想要更新到新版本的话，可以试试[这个方法](https://github.com/KirstieJane/STEMMRoleModels/wiki/Syncing-your-fork-to-the-original-repository-via-the-browser)，或者你也可以干脆删掉重来，只要保留自己的大部分config设定和所有的post就好。

LOFFER只是容器，你的posts才是博客的核心。


## 注意

LOFFER是一个**博客模板**，使用GitHub Pages发布个人博客是没有任何问题的。 **但是:**

- **请勿发布成人向内容** 
- **不要将大量图片上传到GitHub**

如有疑问，请阅读[GitHub Pages官方说明](https://pages.github.com/)。

另外，同人作品更好的发布平台是[AO3](https://archiveofourown.org/)，你想你发在AO3还有tag还有kudos还有人看，是吧？


## 如何使用

首先，这个博客主题适应手机阅读，但是，要使用它建立你自己的博客，你需要上电脑操作。

### 第一步 Fork到你的GitHub

请点击[GitHub](https://github.com/)，注册一个GitHub账户。我们可以理解Git就是个文件版本管理系统，本身并不需要会代码即可使用。

现在你看到的LOFFER，是作为一个GitHub上的Repository（代码库）存在的，你可以把这个代码库复制到你自己的GitHub账户中，这个操作叫做Fork。

点击[LOFFER](https://github.com/FromEndWorld/LOFFER)，进入LOFFER的GitHub Repository页面，然后点Fork：

![gif](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/fork.gif)

然后你立刻就可以看到LOFFER再次出现，这次它已经属于你了，这里我建议你重命名它，点击settings，给你的博客起个名字（请尽量使用字母而非中文）。

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/rename.png)

然后，向下拉页面，你会看到“GitHub Pages”，这是GitHub内置的网站host服务，选择master，如图所示：

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/pages.png)

在几秒钟后，刷新此页面，你通常会看到这个绿色的东西（如果没看到，多等一会），你的网站已经发布成功，点击这个链接，即可查看：

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/published.png)

你可能会看到网站长得很丑，请继续下一步.

### 第二步 设置站点信息

在你的博客的GitHub代码库页面里，选择Code，文件列表里选择_config.yml，点击打开，点击右上角笔形图标修改文档。

修改完成后，点击“Commit changes”。每次修改过代码库并且commit后，GitHub Pages都会自动重新发布网站，只要等上几分钟，再次刷新你的博客页面，就会看到你的修改了。

还有一点，**LOFFER使用的是MIT协议，大意就是全部开源随意使用，如果你要保留自己博文的权利，请编辑LICENSE文件，写上类似“_posts中的文档作者保留权利”这样的内容。**

### 第三步 发布博文

在你的博客的GitHub代码库页面里，点开_posts文件夹，这里面就是你的博客文章。

这些文章使用的格式是Markdown，文件后缀名是md，这是一种非常简单易用的有格式文本标记语言，你应该已经注意到，在LOFFER自带的示例性博文中有一篇中文的Markdown语法介绍。

更简单的办法是使用[Typora](https://typora.io/)，这是一个全图形化界面，全实时预览的Markdown写作软件，非常轻量，而且免费。

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/Typora.png)

在发布博文前，你需要在文章的头部添加这样的内容，包括你的文章标题，发布日期，作者名，和tag等。

    ---
    layout: post
    title: LOFFER文档
    date: 2019-06-02
    Author: 来自中世界
    categories: 
    tags: [sample, document]
    comments: true
    --- 

完成后，保存为.md文件，文件名是date-标题，例如 2019-06-02-document.md (注意这里的标题会成为这个post的URL，所以推荐使用字母而非中文，它不影响页面上显示的标题)，然后上传到_posts文件夹，commit，很快就可以在博客上看到新文章了。

### 可选：图片怎么办？

少量图片可以上传到images文件夹，然后在博文中添加。

但是GitHub用来当做图床有滥用之嫌，如果你的博客以图片为主，建议选择外链图床，例如[sm.ms](https://sm.ms/)就是和很好的选择。

如果想要寻找更适合自己的图床，敬请Google一下。

在博文中添加图片的Markdown语法是：`![图片名](URL)`

### 可选：添加评论区

#### Disqus

LOFFER支持Disqus评论，虽然Disqus很丑，但是它是免费的，设置起来又方便，因此大家也就不要嫌弃它。

首先，注册一个[Disqus](https://disqus.com/)账户，我们可以选择这个免费方案：

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/Disqus-plan.png)

注册成功后，新建一个站点（site），以LOFFER为例设置步骤如下：

首先站点名LOFFER，生成了shortname是loffer，类型可以随便选。

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/Disqus-1.png)

安装时选择Jekyll。

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/Disqus-2.png)

最后填入你的博客地址，语言可以选中文，点Complete，即可！

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/Disqus-3.png)

然后需要回到你的博客，修改_config.yml文件，在disqus字段填上你的shortname，commit，完成！

#### Gitalk

新增内容，LOFFER 0.2.0版本支持Gitalk评论区（在LOFFER示例站中仍然是Disqus，可以在[我的博客](https://himring.top/gitalk/)查看Gitalk的demo），设置方法如下：

首先，创建一个[OAuth application](https://github.com/settings/applications/new), 设置如图：

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/application_settings.png)

点Register后就会看到你所需要的两个值，clientID和clientSecret，把它们复制到你的_config.yml文件中相应的字段：

    gitalk:
      clientID: <你的clientID>
      clientSecret: <你的clientSecret>
      repo: <你的repository名称>
      owner: <你的GitHub用户名>

然后commit，你的Gitalk评论区就会出现了。对于每一篇文章，都需要你来进入文章页，来初始化评论区，这一操作会在你的repository上创建一个Issue，此后的评论就是对这个Issue的回复。

你可以进入你的repository的Issue页面，点**Unsubscribe**来避免收到大量相关邮件。

注意：出于很明显的原因，最好不要同时添加Disqus和Gitalk评论区。

### 导入LOFTER的内容

这部分由于LOFTER的导出文件十分~~优秀~~，需要另外解决。

诸位可以使用[墨问非名太太的脚本](http://underdream.lofter.com/post/38ea7d_1c5d8a983)，其中选择Jekyll输出即可。

我个人也在折腾一个脚本，目前还没有完全debug清楚，不管如何，请先在lofter里导出一下，存在本地也是好的，贴吧可以让2017以前所有内容全部消失，中国互联网，没什么不可能发生的。

## 致谢

* [Jekyll](https://github.com/jekyll/jekyll) - 这是本站存在的根基
* [Kiko-now](<https://github.com/aweekj/kiko-now>) - 我首先是fork这个主题，然后再其上进行修改汉化，才有了LOFFER
* [Font Awesome](<https://fontawesome.com/>) - 社交网络图标来自FontAwesome的免费开源内容



## 帮助这个项目

介绍更多人来使用它，摆脱lofter自由飞翔！

当然如果单说写同人的话，我还是建议大家都去AO3，但是自家博客自己架也很酷炫，你还可以选择很多其他的forkable Jeykll主题，GitHub上有很多，或者试试其他博客架设工具，例如Hexo，与代码斗其乐无穷。

最后，回到[LOFFER](https://github.com/FromEndWorld/LOFFER)，给我点一个☆吧！

![img](https://raw.githubusercontent.com/FromEndWorld/LOFFER/master/images/givemefive.png)
