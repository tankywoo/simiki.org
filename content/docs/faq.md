---
title: "FAQ"
date: 2013-10-12 00:00
---

### Use Simiki in Windows ###

Simiki is not good support on Windows. If possible, use it under `Unix` / `Linux` / `Mac`.

If use [Fabric](http://www.fabfile.org/), some problems maybe happened, make sure the following package are installed:

[`pycrypto`](http://www.voidspace.org.uk/python/modules.shtml#pycrypto):

	easy_install http://www.voidspace.org.uk/downloads/pycrypto26/pycrypto-2.6.win32-py2.7.exe

[`ecdsa`](https://pypi.python.org/pypi/ecdsa/):

	pip install ecdsa

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

### Feed ###

***NOTE***:

1. Only support Atom by now, not support RSS2.0
2. Not a stable feature, may have changes later

Put `atom.xml` under wiki directory:

```xml
<?xml version="1.0" encoding="utf-8"?>
{% if site.url %}
  {% set site_url = "%s%s"|format(site.url, site.root) %}
{% else %}
  {% set site_url = site.url %}
{% endif %}
<feed xmlns="http://www.w3.org/2005/Atom">
  <generator uri="http://simiki.org/" version="{{ site.version }}">Simiki</generator>
  <title>{{ site.title }}</title>
  <link href="{{ site_url }}/" />
  <link href="{{ site_url }}/atom.xml" rel="self" type="application/atom+xml" />
  <updated>{{ site.time|rfc3339 }}</updated>
  <id>{{ site_url }}</id>
  <author>
    <name>{{ site.author|e }}</name>
  </author>
  {% for f, page in pages.iteritems() %}
    {% set uri = site_url ~ f|replace('content/', '/', 1)|replace('.md', '.html', 1) %}
  <entry>
    <id>{{ uri }}</id>
    <title>{{ page.title|e }}</title>
    <link href="{{ uri }}" />
    <published>{{ page.date|rfc3339 }}</published>

    {% if page.updated %}
    <updated>{{ page.updated|rfc3339 }}</updated>
    {% else %}
    <updated>{{ page.date|rfc3339 }}</updated>
    {% endif %}

    {% if page.category %}
    <category term="{{ page.category }}" />
    {% endif %}

    {% if page.content %}
    <content type="html">{{ page.content|e }}</content>
    {% endif %}
    {% if page.summary %}
    <summary>{{ page.summary|e }}</summary>
    {% endif %}
  </entry>
  {% endfor %}
</feed>
```

Add this line between `<head>` and `</head>` of theme's `base.html` file:

```html
<link rel="alternate" type="application/atom+xml" href="atom.xml" title="Atom feed">
```

### Favicon ###

(Version v1.5.0.post1)

Put the icon file named `favicon.ico` to the top directory of wiki.

And the theme need to set:

	<link rel="shortcut icon" href="{{ site.root }}/favicon.ico" type="image/x-icon">
	<link rel="icon" href="{{ site.root }}/favicon.ico" type="image/x-icon">
