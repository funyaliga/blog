---
layout: post
title:  "Sublime Text 2 备忘录"
date:   2012-12-08 10:29:21
category: tool
permalink: /12128
uid: 12128
---

### 推荐资料 ###

*   Sublime Text教程：<http://kevintsengtw.blogspot.com/p/sublime-text-2.html>
*   设置文件详解：<http://www.feelcss.com/sublime-text-2-settings.html>

### package control安装 ###
<pre>
view->show console （快捷键Ctrl+`）调出console

黏贴下面代码，回车
import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print 'Please restart Sublime Text to finish installation'

重启软件后，在 Perferences 有 package control 就是成功了
</pre>

### 安装Zen Coding ###
<!-- read more -->
<pre>
Perferences->package control（快捷键：ctrl+shift+p）
输入install
搜索 emmet (原ZenCoding，现在已经改名为emmet )
</pre>

### 我的配置 ###
<pre>
{
	"caret_style": "phase",
	"fade_fold_buttons": false,
	"font_face": "YaHei Consolas Hybrid",
	"font_size": 9,
	"highlight_line": true,
	"ignored_packages":
	[
		"Vintage"
	],
	"line_padding_bottom": 1,
	"line_padding_top": 1,
	"margin": 4,
	"tab_size": 4,
	"word_wrap": true
}
</pre>