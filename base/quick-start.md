---
layout: post
title: "Quick Start"
date: 2013-12-08 22:30
---

Simiki Version : `0.1.0`

## 安装 Simiki ##

	pip install simiki

或者

	python setup.py install

## 配置文件 ##

	mkdir mywiki
	cd mywiki

接着下载配置文件:

	wget https://raw.github.com/tankywoo/simiki/master/simiki/conf_templates/_config.yml.in -O _config.yml

编辑配置文件, 主要是下面几项:

	url: http://simiki.org
	title: Simiki
	keywords: simiki, wiki, python, web, code
	description: Simiki is a simple static site generator for wiki.
	author: Tanky Woo

## 构建站点 ##

	simiki build_site

生成 `content` 和 `html` 两个目录, `content` 目录是存放 `Markdown` 源文件, `html` 是生成的静态文件.

接着会把相应主题的css等文件复制到 `html` 目录下.

## 新建一篇 wiki ##

	simiki new_wiki -c base -t 'Quick Start'

新建一篇 wiki, 目录是 base, wiki 的标题是 "Quick Start". 文件名会自动识别为 quick-start.md, 存放在 html/base/quick-start.md.

也可以通过 `-f` 参数手动指定文件名.

然后就可以打开相应文件撰写 wiki 了.

## 生成/更新静态页面 ##

	simiki generate
