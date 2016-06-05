---
title: "Code Highlight"
date: 2013-10-12 00:00
---

Code highlight of Simiki use [Pygments](http://pygments.org/), a powerful syntax highlighter.

## Highlight CSS ##

Use [Pygments](http://pygments.org/) to generate syntax css.

In general the theme will include syntax css file.

	# Get the color themes list
	pygmentize -L styles

	# Generate syntax css file
	pygmentize -f html -S <colortheme name> -a .hlcode > syntax.css

## Use Code Highlight Feature ##

**Note**: Make sure you are familiar with the syntax of [Markdown](https://daringfireball.net/projects/markdown/)

(Below example, `-` represent a space)

***`indented code blocks`*** is the simplest way, with a tab indentation, and have `Shebang`:

```python
----#!/usr/bin/env python
----# -*- coding: utf-8 -*-

----if __name__ == "__main__":
--------print("Hello World!")
```

The result:

	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")


***`fenced code blocks`*** include some different style listed below:

PHP extra's syntax, with four tilde at begin and end:

```python
~~~~
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~
```

The result:

~~~~
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

At the same time you can define a language([Supported languages](http://pygments.org/languages/) and [Short Names](http://pygments.org/docs/lexers/)):

```python
~~~~{.python}
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

########### OR ###########

~~~~.python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~
```

The result:

~~~~{.python}
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

Github fenced code blocks, with three back-quote at begin and end, with no indentation:

	```python
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	```

The result:

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
```

In the end, you can highlight specified lines:

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

The result:

```python hl_lines="1 3"
import sys

if __name__ == __main__:
	sys.exit()
```

More detailed usage can be seen in [Python-Markdown](https://pythonhosted.org/Markdown/) document:

* [Fenced Code Blocks](https://pythonhosted.org/Markdown/extensions/fenced_code_blocks.html)
* [CodeHilite](https://pythonhosted.org/Markdown/extensions/code_hilite.html)
