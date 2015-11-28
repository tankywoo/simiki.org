---
title: "FAQ"
date: 2013-10-12 00:00
---

## FAQ ##

### Use Simiki in Windows ###

Simiki is not good support on Windows. If possible, use it under `Unix` / `Linux` / `Mac`.

If use [Fabric](http://www.fabfile.org/), some problems maybe happened, make sure the following package are installed:

[`pycrypto`](http://www.voidspace.org.uk/python/modules.shtml#pycrypto):

	easy_install http://www.voidspace.org.uk/downloads/pycrypto26/pycrypto-2.6.win32-py2.7.exe

`ecsda`:

	pip install ecsda

Reference:

* [Fabric installs but doesn’t run!](http://www.fabfile.org/faq.html#fabric-installs-but-doesn-t-run)
* [Fabric 1.8.4 and 1.9.0 don't work on OS X 10.9](https://github.com/fabric/fabric/issues/1157)
* [simiki issue #34](https://github.com/tankywoo/simiki/issues/34)

### Custom Index ###

Simiki will auto generate an index page by default. If there is a file named `index.md` under `source` directory, Simiki will use this page as index content.

### Support TOC? ###

Yes, support TOC (Table Of Content). Add a line `[TOC]` between YAML Front Matter and content:

	---
	title: "Hello World"
	date: 2015-01-01 00:00
	---

	[TOC]

	<your content>
