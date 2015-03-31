---
layout: page
title: "FAQ"
date: 2015-01-13 01:06
---

## FAQ ##

### Use Simiki in Windows ###

Simiki is not good support on Windows. If possible, use it under Unix/Linux/Mac.

Under Windows, you should install [`pycrypto`](http://www.voidspace.org.uk/python/modules.shtml#pycrypto)(used by [`Fabric`](http://www.fabfile.org/), maybe remove in later version):

	easy_install http://www.voidspace.org.uk/downloads/pycrypto26/pycrypto-2.6.win32-py2.7.exe

and `ecsda`:

	pip install ecsda

### Custom Index ###

Simiki will auto generate an index page by default. If there is a file named `index.md` under `source` directory, Simiki will use this page as index content.

Before version `1.3`, custom index is defind by setting `index: path/to/file`, and it was removed by now, I don't suggest use custom index by this way.
