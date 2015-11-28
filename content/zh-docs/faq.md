---
title: "FAQ"
date: 2013-10-12 00:00
---

### Windows下使用Simiki ###

Simiki对Windows的支持不是很好, 如果可能, 请尽量选择在 `Unix` / `Linux` / `Mac` 下使用.

如果使用[Fabric](http://www.fabfile.org/index.html), 可能会出现一些问题, 首先确认安装了以下模块:

[`pycrypto`](http://www.voidspace.org.uk/python/modules.shtml#pycrypto):

	easy_install http://www.voidspace.org.uk/downloads/pycrypto26/pycrypto-2.6.win32-py2.7.exe

`ecsda`:

	pip install ecsda

参考:

* [Fabric installs but doesn’t run!](http://www.fabfile.org/faq.html#fabric-installs-but-doesn-t-run)
* [Fabric 1.8.4 and 1.9.0 don't work on OS X 10.9](https://github.com/fabric/fabric/issues/1157)
* [simiki issue #34](https://github.com/tankywoo/simiki/issues/34)

### 自定义首页 ###

Simiki默认会自动生成首页.

如果想自定义首页, 可以在`source`目录下创建`index.md`, Simiki会生成相应的自定义首页.

### 对TOC的支持吗? ###

是的, 支持 TOC (Table Of Content). 在YAML Front Matter下面, wiki内容的顶部，添加一行即可:

	---
	title: "Hello World"
	date: 2015-01-01 00:00
	---

	[TOC]

	<your content>
