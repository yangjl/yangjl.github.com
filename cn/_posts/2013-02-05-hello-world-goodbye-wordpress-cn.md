---
layout: post
title: 暂别wordpress， kiss goodbye.
categories: [Emacs]
tags: [markdown-mode, ibus, emacs, 静态页面]
---

自从微软把我亲爱的space搞死以后我就把博客转移到了hostmonster用wordpress来继续书
写， 然而打那之后少了msn的支持写博客的热情也少了许多，诸如微薄等新媒体的出现更是
把自己的懒惰暴露无疑。每天能可写几十条20几个字的信息，也不愿一篇100字的博文。所
以。。。我的各种写作能力都逐渐弱智向了。。

新年一时兴起重新折腾wordpress，发现自己对速度的忍耐极限不知道何时已经挑剔的令人发
指，看自己博客加载超过1秒都捉急的不行。期间尝试选用各种简化主题和cache插件，效果
依旧不敢恭维。在家上N多人都在用静态页面，比如益辉，简洁可爱的令人发指，同时也快
的令人发指。然而，哥，依旧懒得彻底重整博客。

终于，压到骆驼的最后一根稻草出现鸟，再尝试过*Emacs*的markdown-mode以后，我已经无
法抵挡用*Emacs*写博客的吸引力。

因为，*Emacs*是邪教，入了就出不去了。指法都已经变形，哥无奈的表示真的已经回不去了。。。
T_T，恨不得gmail都装*Emacs*的组合键位。

接下来插播下markdown-mode的安装方法，原文
[这里](http://jblevins.org/projects/markdown-mode/), 方法入下。

讲markdown-mode.el克隆到.emacs.d目录下，

{% highlight bash %}
git clone git://jblevins.org/git/markdown-mode.git
{% endhighlight %}

然后修改.emacs文件，加入如下几行

{% highlight bash %}
(add-to-list 'load-path "~/.emacs.d/")
(autoload 'markdown-mode "markdown-mode"
   "Major mode for editing Markdown files" t)
(add-to-list 'auto-mode-alist '("\\.md\\'" . markdown-mode))
{% endhighlight %}

注：`.md` 可改成其他你希望启动markdown模式的文件格式。

C-c C-c p既可预览。

Ok，解释完了稻草，我接下来就直接无耻的fork了益辉的博客的github page。。。然后简单
做了必要修改，调整了CSS，就直接publish之。谢谢谢老师！（我木有口吃！）

如果你使用ibus管理使用输入法，再附上Ubuntu（12.10其他版本未验证）下Emacs使用
ibus.el的方法，也十分简单

首先安装ibus.el
{% highlight bash %}
sudo apt-get install ibus-el
{% endhighlight %}

.emacs里满加入
{% highlight bash %}
;; ibus
(require 'ibus)
 (add-hook 'after-init-hook 'ibus-mode-on)
{% endhighlight %}

然后用你熟悉的ibus组合键调出你的输入法即可。

欧了，以后就这么地了，这就删了wordpress去～
