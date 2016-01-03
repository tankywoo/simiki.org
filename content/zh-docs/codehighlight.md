---
title: "代码高亮"
date: 2013-10-12 00:00
---

代码高亮使用的是 [Pygments](http://pygments.org/) 库. 一个强大的代码语法高亮套件.

## 配色主题 ##

首先生成自己喜欢的高亮配色主题CSS样式文件.

主题一般都会自带代码高亮样式文件.

	# 获取高亮配色主题列表
	pygmentize -L styles

	# 生成高亮配色主题CSS文件
	pygmentize -f html -S [colortheme name] -a .hlcode > syntax.css

## wiki使用语法高亮 ##

**注意**: 首先保证熟悉Markdown的语法格式


***`indented code blocks`***. 最简单的方式, 缩进一个tab并且代码顶部有[`Shebang`](https://en.wikipedia.org/wiki/Shebang\_(Unix)):

```python
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
```

效果如下:

	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")

***`fenced code blocks`***, 包括以下几种风格:

PHP extra's syntax, 上下各四个波浪号:

```python
~~~~
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~
```

效果如下:

~~~~
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

同时还可以指定语言类型([支持的语言](http://pygments.org/languages/)和[标签名称](http://pygments.org/docs/lexers/)):

```python
~~~~{.python}
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

########### 或者 ###########

~~~~.python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~
```

效果如下

~~~~{.python}
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

Github fenced code blocks, 用三个反引号将代码块前后阔起来, 不需要缩进:

	```python
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	```

效果如下

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
```

最后, 代码高亮还可以进一步通过背景颜色高亮指定的行:

	~~~~{.python hl_lines="1 3"}
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	~~~~

	########### 或者 ###########

	```python hl_lines="1 3"
	import sys

	if __name__ == __main__:
		sys.exit()
	```

效果如下:

```python hl_lines="1 3"
import sys

if __name__ == __main__:
	sys.exit()
```

更多详细的使用方法可以见 [Python-Markdown](https://pythonhosted.org/Markdown/) 的文档:

* [Fenced Code Blocks](https://pythonhosted.org/Markdown/extensions/fenced_code_blocks.html)
* [CodeHilite](https://pythonhosted.org/Markdown/extensions/code_hilite.html)
