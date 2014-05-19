---
layout: page
title: "Code Highlight"
---

Use [Pygments](http://pygments.org/) to generate syntax css:

Get the color theme name:

	pygmentize -L styles

Generate css:

	pygmentize -f html -S [colortheme name] -a .hlcode > syntax.css

The simplest way is to use `indented code blocks`.

	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")

Or use `fenced code blocks`.

PHP extra's syntax:

	~~~~
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	~~~~

~~~~
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

Define a language:

	~~~~{.python}
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	~~~~

~~~~{.python}
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

or:

	~~~~.python
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	~~~~

~~~~.python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
~~~~

Github fenced code blocks:

	```python
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	```

```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

if __name__ == "__main__":
	print("Hello World!")
```

<!-- -->

Highlight some lines:

	~~~~{.python hl_lines="1 3"}
	#!/usr/bin/env python
	# -*- coding: utf-8 -*-

	if __name__ == "__main__":
		print("Hello World!")
	~~~~

or:

	```python hl_lines="1 3"
	import sys

	if __name__ == __main__:
		sys.exit()
	```

```python hl_lines="1 3"
import sys

if __name__ == __main__:
	sys.exit()
```

More detailed usage can be seen in [Python-Markdown] doc:

* [Fenced Code Blocks]()
* [CodeHilite]()
